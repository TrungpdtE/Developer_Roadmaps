# Project tổng hợp: Student Enrollment Platform

Project này dùng để nối tất cả mảng trong roadmap thành một sản phẩm nhỏ nhưng có đủ chất backend thật.

## Mục tiêu

Xây hệ thống cho sinh viên đăng ký môn học:

- Admin tạo sinh viên.
- Admin tạo môn học và số lượng chỗ.
- Sinh viên đăng ký môn.
- Hệ thống không cho đăng ký trùng.
- Hệ thống không cho đăng ký khi môn đã đầy.
- Hệ thống ghi log, có test, có database, có cache và có event.

## Stack khuyến nghị

- Java 25 LTS hoặc Java 21 LTS nếu môi trường/framework của bạn ổn định hơn với 21.
- Spring Boot.
- Maven hoặc Gradle, chọn một.
- PostgreSQL.
- Hibernate/JPA.
- JUnit 5, AssertJ, Mockito.
- Testcontainers cho integration test.
- Caffeine cache.
- RabbitMQ hoặc Kafka sau khi phần CRUD đã ổn.

## Domain model

```java
public class Student {
    private final String studentCode;
    private String fullName;

    public Student(String studentCode, String fullName) {
        if (studentCode == null || studentCode.isBlank()) {
            throw new IllegalArgumentException("Student code is required");
        }
        if (fullName == null || fullName.isBlank()) {
            throw new IllegalArgumentException("Full name is required");
        }
        this.studentCode = studentCode;
        this.fullName = fullName;
    }
}
```

## API cần có

```text
POST   /api/students
GET    /api/students/{studentCode}
POST   /api/courses
GET    /api/courses/{courseCode}
POST   /api/enrollments
GET    /api/students/{studentCode}/enrollments
```

## Database schema gợi ý

```sql
create table students (
    id bigserial primary key,
    student_code varchar(30) not null unique,
    full_name varchar(200) not null,
    created_at timestamp not null default current_timestamp
);

create table courses (
    id bigserial primary key,
    course_code varchar(30) not null unique,
    title varchar(200) not null,
    capacity integer not null check (capacity > 0),
    created_at timestamp not null default current_timestamp
);

create table enrollments (
    id bigserial primary key,
    student_id bigint not null references students(id),
    course_id bigint not null references courses(id),
    status varchar(30) not null,
    created_at timestamp not null default current_timestamp,
    unique (student_id, course_id)
);
```

## Service rule quan trọng

```java
public class EnrollmentService {
    private final StudentRepository studentRepository;
    private final CourseRepository courseRepository;
    private final EnrollmentRepository enrollmentRepository;
    private final EnrollmentEventPublisher enrollmentEventPublisher;

    public EnrollmentService(
            StudentRepository studentRepository,
            CourseRepository courseRepository,
            EnrollmentRepository enrollmentRepository,
            EnrollmentEventPublisher enrollmentEventPublisher
    ) {
        this.studentRepository = studentRepository;
        this.courseRepository = courseRepository;
        this.enrollmentRepository = enrollmentRepository;
        this.enrollmentEventPublisher = enrollmentEventPublisher;
    }

    public EnrollmentResult enroll(String studentCode, String courseCode) {
        Student student = studentRepository.findByStudentCode(studentCode)
                .orElseThrow(() -> new IllegalArgumentException("Student not found"));

        Course course = courseRepository.findByCourseCode(courseCode)
                .orElseThrow(() -> new IllegalArgumentException("Course not found"));

        if (enrollmentRepository.existsByStudentAndCourse(student, course)) {
            throw new IllegalStateException("Student already enrolled in this course");
        }

        int currentEnrollmentCount = enrollmentRepository.countByCourse(course);
        if (currentEnrollmentCount >= course.getCapacity()) {
            throw new IllegalStateException("Course is full");
        }

        Enrollment enrollment = enrollmentRepository.save(new Enrollment(student, course));
        enrollmentEventPublisher.publishStudentEnrolled(enrollment);

        return new EnrollmentResult(enrollment.getId(), studentCode, courseCode);
    }
}
```

## Test bắt buộc

- `enrollShouldCreateEnrollmentWhenCourseHasCapacity`
- `enrollShouldRejectDuplicateEnrollment`
- `enrollShouldRejectWhenCourseIsFull`
- `findStudentShouldReturn404WhenStudentDoesNotExist`
- `repositoryShouldPersistEnrollment`
- `eventConsumerShouldIgnoreDuplicateEvent`

## Production checklist

- Có request validation.
- Có global exception handler.
- Có transaction ở service method ghi dữ liệu.
- Có log request id.
- Có migration versioned.
- Có test chạy bằng build tool.
- Không log token/password.
- Không expose entity JPA trực tiếp ra API.
- Có README hướng dẫn chạy local.

[Quay lại README](README.md)
