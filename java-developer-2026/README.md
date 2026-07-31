# Java Developer in 2026

Folder này tách riêng với roadmap Java core trước đó. Nó bám theo ảnh `java-developer-roadmap.png`: không chỉ học ngôn ngữ Java, mà học cả hệ sinh thái để đi làm backend Java.

![Java Developer Roadmap 2026](../java-developer-roadmap.png)

## Cách dùng roadmap này

1. Học nhóm **Learn the Prerequisites** trước.
2. Sau đó học **General Development Skills**, **Databases**, **Testing**, **Logging**.
3. Chọn **Spring + Hibernate + PostgreSQL + JUnit + Testcontainers** làm stack chính để luyện project đầu tiên.
4. Các mục **Good to know** học để đọc hiểu hệ sinh thái; các mục **Possibilities** chỉ cần biết tên/use case trước.
5. Mỗi file đều có lý thuyết, facts, ví dụ code/cấu hình, cách triển khai thực tế, lỗi hay gặp và checklist tự học.

## Thống kê

- Tổng số bài: **123**
- Personal must know: **69**
- Good to know: **46**
- Possibilities: **8**

## Lộ trình học gợi ý cho sinh viên

### Giai đoạn 1: Nền tảng bắt buộc

- Java CLI, syntax, package, interface, exception, thread/virtual thread.
- Maven hoặc Gradle.
- SQL căn bản.
- Git, HTTP/HTTPS, DSA căn bản.

### Giai đoạn 2: Backend thực chiến

- Spring.
- PostgreSQL.
- Hibernate/JPA.
- REST API.
- Logging bằng SLF4J/Log4j2 hoặc Logback.
- Unit test với JUnit, AssertJ, Mockito.
- Integration test với Testcontainers/WireMock.

### Giai đoạn 3: Hệ thống production

- Cache: Caffeine, Redis.
- Message broker: RabbitMQ hoặc Kafka.
- Search: Elasticsearch/OpenSearch.
- Monitoring/log management: ELK, Sentry.
- API client: OkHttp/Retrofit, GraphQL nếu dự án cần.

### Giai đoạn 4: Nâng cao

- Microservices, RPC, gRPC, Protobuf.
- Workflow engine: Temporal.
- AI/LLM với langchain4j, vector database, RAG.
- Design patterns, stability patterns, concurrency patterns.

## Roadmap Clickable

### Learn the Prerequisites

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Java CLI](topics/java-cli.md) | Personal must know | Biết dùng terminal để compile, chạy, truyền argument, kiểm tra version và debug lỗi môi trường Java. |
| [Variables, Constants, Types, Functions, Packages](topics/variables-constants-types-functions-packages.md) | Personal must know | Nền tảng cú pháp Java: biến, hằng, kiểu dữ liệu, function/method và package để tổ chức source code. |
| [Array and ArrayList](topics/array-and-arraylist.md) | Personal must know | Cấu trúc dữ liệu tuyến tính cơ bản nhất trong Java, dùng để lưu nhiều phần tử cùng kiểu hoặc cùng interface. |
| [Pointers, Class, Methods](topics/pointers-class-methods.md) | Personal must know | Java không có pointer kiểu C/C++, nhưng có reference. Chủ đề này giúp hiểu object, class, method và tham chiếu. |
| [Interface](topics/interface.md) | Personal must know | Interface là contract để code phụ thuộc vào hành vi thay vì phụ thuộc implementation cụ thể. |
| [Thread, Routine](topics/thread-routine.md) | Personal must know | Nắm thread, task, executor và cách Java chạy nhiều công việc đồng thời. |
| [Exception Handling](topics/exception-handling.md) | Personal must know | Cơ chế xử lý lỗi trong Java bằng checked exception, unchecked exception, try-catch và custom exception. |
| [Virtual Threads](topics/virtual-threads.md) | Personal must know | Tính năng Java hiện đại giúp viết code blocking dễ đọc nhưng xử lý nhiều tác vụ I/O với chi phí thread thấp. |
| [Gradle/Maven, Library](topics/gradle-maven-library.md) | Personal must know | Biết build project, khai báo dependency, chạy test, đóng gói artifact và quản lý thư viện. |
| [Java Dependency Management Tool](topics/java-dependency-management-tool.md) | Personal must know | Hiểu Maven/Gradle tải dependency từ repository, giải quyết transitive dependency và scope/configuration. |
| [Semantic Versioning](topics/semantic-versioning.md) | Personal must know | Quy tắc version MAJOR.MINOR.PATCH để hiểu khi nào nâng cấp thư viện có thể phá tương thích. |
| [Version, Scripts, Repository and Properties](topics/version-scripts-repository-and-properties.md) | Personal must know | Cấu hình version Java, scripts build, repository Maven, properties và profile trong build tool. |
| [SQL Fundamentals](topics/sql-fundamentals.md) | Personal must know | Nền tảng truy vấn database quan hệ: table, row, column, SELECT, JOIN, index, transaction. |
| [Basic SQL Syntax](topics/basic-sql-syntax.md) | Personal must know | Cú pháp SQL tối thiểu để đọc/ghi dữ liệu và debug query sinh ra từ ORM. |

### General Development Skills

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [GIT](topics/git.md) | Personal must know | Version control bắt buộc cho dev: commit, branch, merge, rebase, pull request và conflict. |
| [HTTP/HTTPS](topics/http-https.md) | Personal must know | Nền tảng mọi REST API/web backend: request, response, header, status code, TLS và cache. |
| [Data Structures and Algorithms](topics/data-structures-and-algorithms.md) | Personal must know | Biết chọn cấu trúc dữ liệu và phân tích độ phức tạp để code không chậm bất ngờ. |
| [Scrum, Kanban or Other Project Strategies](topics/scrum-kanban-or-other-project-strategies.md) | Good to know | Hiểu cách team chia việc, theo dõi tiến độ, review và giao phần mềm theo sprint/flow. |
| [Basic Authentication, OAuth, JWT](topics/basic-authentication-oauth-jwt.md) | Personal must know | Các cơ chế xác thực/phân quyền phổ biến trong backend API hiện đại. |
| [SOLID, YAGNI, KISS, DRY](topics/solid-yagni-kiss-dry.md) | Personal must know | Nguyên tắc thiết kế giúp code dễ hiểu, dễ sửa, không over-engineer. |

### CLI

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [CLI](topics/cli.md) | Personal must know | Tạo command-line app trong Java để chạy tool, batch job, script nội bộ. |
| [JCommander](topics/jcommander.md) | Personal must know | Thư viện parse command-line arguments dựa trên annotation. |
| [airline](topics/airline.md) | Good to know | Thư viện CLI parser hỗ trợ command/subcommand, phù hợp tool nhiều lệnh. |

### Web Frameworks + Routers

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Spring](topics/spring.md) | Personal must know | Framework backend Java quan trọng nhất để xây REST API, service, data access, security và cloud app. |
| [Helidon](topics/helidon.md) | Personal must know | Framework microservice Java của Oracle, có SE/MP, phù hợp cloud-native service. |
| [Spark](topics/spark.md) | Good to know | Micro web framework nhẹ cho Java/Kotlin, học routing HTTP nhanh. |
| [dropwizard](topics/dropwizard.md) | Good to know | Framework service Java opinionated, tích hợp Jetty, Jersey, Jackson, metrics. |
| [nanohttpd](topics/nanohttpd.md) | Good to know | HTTP server nhỏ gọn, phù hợp nhúng server đơn giản hoặc demo. |

### ORMs

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Hibernate](topics/hibernate.md) | Personal must know | ORM phổ biến nhất trong Java, triển khai JPA và xử lý entity, persistence context, lazy loading. |
| [Ebean](topics/ebean.md) | Good to know | ORM Java thay thế JPA/Hibernate trong một số codebase, tập trung đơn giản hóa query/entity. |

### Databases

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Databases](topics/databases.md) | Personal must know | Bức tranh tổng quan về lưu trữ: relational, NoSQL, search engine, cloud database và use case. |
| [Relational](topics/relational.md) | Personal must know | Database quan hệ dùng SQL, schema, constraint, transaction, index và JOIN. |
| [SQL Server](topics/sql-server.md) | Good to know | RDBMS của Microsoft, thường gặp trong enterprise và hệ sinh thái .NET/Windows. |
| [MySQL](topics/mysql.md) | Good to know | RDBMS phổ biến cho web app, dễ học, nhiều hosting hỗ trợ. |
| [MariaDB](topics/mariadb.md) | Possibilities | Fork/alternative của MySQL, tương thích nhiều use case MySQL. |
| [PostgreSQL](topics/postgresql.md) | Personal must know | RDBMS mạnh, chuẩn, phổ biến cho backend hiện đại, hỗ trợ JSONB, index nâng cao, extension. |
| [Cloud Databases](topics/cloud-databases.md) | Good to know | Database được quản lý bởi cloud provider, giảm vận hành nhưng cần hiểu cost, latency, backup, region. |
| [Azure CosmosDB](topics/azure-cosmosdb.md) | Personal must know | Cloud database multi-model của Azure, nổi bật ở phân tán toàn cầu và consistency levels. |
| [Amazon DynamoDB](topics/amazon-dynamodb.md) | Good to know | NoSQL key-value/document database serverless của AWS, thiết kế theo access pattern. |
| [NoSQL](topics/nosql.md) | Good to know | Nhóm database không thuần quan hệ: document, key-value, wide-column, time-series, graph/vector. |
| [MongoDB](topics/mongodb.md) | Personal must know | Document database phổ biến, lưu JSON-like document, linh hoạt schema. |
| [Redis](topics/redis.md) | Personal must know | In-memory data store dùng cho cache, rate limit, queue nhẹ, session và distributed lock cẩn thận. |
| [Clickhouse](topics/clickhouse.md) | Good to know | Column-oriented database cho analytics/OLAP, query dữ liệu lớn rất nhanh khi model đúng. |
| [Apache Cassandra](topics/apache-cassandra.md) | Good to know | Wide-column distributed database cho write-heavy workload và availability cao. |
| [InfluxDB](topics/influxdb.md) | Good to know | Time-series database cho metrics, sensor data, monitoring. |
| [CouchDB](topics/couchdb.md) | Possibilities | Document database có replication/sync model, dùng trong một số hệ offline-first. |
| [Weaviate](topics/weaviate.md) | Personal must know | Vector database phục vụ semantic search và AI/RAG. |
| [Search Engines](topics/search-engines.md) | Good to know | Hệ thống tìm kiếm full-text, ranking, indexing, filtering và analytics. |
| [ElasticSearch](topics/elasticsearch.md) | Personal must know | Search engine phổ biến dựa trên Lucene, dùng cho search/log analytics. |
| [Opensearch](topics/opensearch.md) | Good to know | Fork mở của Elasticsearch, thường dùng trong AWS/OpenSearch ecosystem. |
| [Algolia](topics/algolia.md) | Possibilities | Search-as-a-service có trải nghiệm developer tốt và ranking/config tiện. |

### Caching

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Caching](topics/caching.md) | Personal must know | Kỹ thuật lưu dữ liệu hay dùng ở tầng nhanh hơn để giảm latency và tải database. |
| [Caffeine](topics/caffeine.md) | Personal must know | Local in-memory cache cho Java, hiệu năng cao, thay thế tốt cho Guava cache trong nhiều use case. |
| [Distributed Cache](topics/distributed-cache.md) | Personal must know | Cache dùng chung giữa nhiều instance service, cần hiểu TTL, invalidation, consistency. |
| [Java-Redis](topics/java-redis.md) | Personal must know | Client Java để dùng Redis như distributed cache/session/rate limiter. |
| [Java-Memcached](topics/java-memcached.md) | Good to know | Client Java cho Memcached, cache key-value đơn giản. |

### Logging

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Log Management System](topics/log-management-system.md) | Good to know | Thu thập, lưu, tìm kiếm, cảnh báo log từ nhiều service. |
| [ELK Stack](topics/elk-stack.md) | Personal must know | Elasticsearch, Logstash, Kibana dùng để ingest/search/visualize log. |
| [Sentry.io](topics/sentry-io.md) | Good to know | Error monitoring giúp gom exception, stack trace, release, user impact. |
| [loggly.com](topics/loggly-com.md) | Possibilities | Cloud log management service, dùng để tập trung log và query. |
| [Log Frameworks](topics/log-frameworks.md) | Personal must know | Biết facade/implementation, log level, structured logging và correlation id. |
| [log4j](topics/log4j.md) | Personal must know | Logging framework Java mạnh; code mới thường dùng Log4j2 hoặc SLF4J facade. |
| [Zap](topics/zap.md) | Possibilities | Zap là logger phổ biến bên Go, trong roadmap này nên biết để đọc hệ thống polyglot, không phải thư viện Java chính. |
| [TinyLog](topics/tinylog.md) | Good to know | Logging framework nhẹ cho Java app/tool nhỏ. |

### Real-Time Communication

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Real-Time Communication](topics/real-time-communication.md) | Personal must know | Giao tiếp realtime bằng WebSocket, SSE, long polling hoặc event streaming. |
| [atmosphere](topics/atmosphere.md) | Personal must know | Framework Java hỗ trợ WebSocket/SSE/long polling abstraction. |
| [webbit](topics/webbit.md) | Personal must know | HTTP/WebSocket server nhỏ, chủ yếu nên biết nếu gặp codebase cũ. |

### API Clients

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [API Clients](topics/api-clients.md) | Personal must know | Gọi API ngoài bằng HTTP client, REST client, GraphQL client, timeout/retry/circuit breaker. |
| [GraphQL](topics/graphql.md) | Good to know | API query language cho phép client chọn field cần lấy, khác REST endpoint cố định. |
| [REST](topics/rest.md) | Personal must know | Kiến trúc API phổ biến nhất: resource, method HTTP, status code, JSON, idempotency. |
| [okhttp](topics/okhttp.md) | Personal must know | HTTP client Java/Kotlin mạnh, phổ biến trong Android và JVM backend. |
| [retrofit](topics/retrofit.md) | Good to know | Type-safe HTTP client dựa trên interface annotation, thường đi với OkHttp. |

### Testing

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Testing](topics/testing.md) | Personal must know | Chiến lược test từ unit, integration đến E2E để giữ code ổn định khi thay đổi. |
| [Unit Testing](topics/unit-testing.md) | Personal must know | Test đơn vị nhỏ, nhanh, độc lập; thường dùng JUnit + AssertJ + Mockito. |
| [Mocking](topics/mocking.md) | Personal must know | Thay dependency bằng mock/fake/stub để test class đang xét trong isolation. |
| [Mockito](topics/mockito.md) | Good to know | Mocking framework phổ biến nhất trong Java unit test. |
| [Frameworks](topics/frameworks.md) | Personal must know | Nhóm test framework và helper library tạo runner, lifecycle, assertion, fixture. |
| [JUnit](topics/junit.md) | Personal must know | Framework unit testing chuẩn de facto trong Java hiện đại. |
| [Citrus Framework](topics/citrus-framework.md) | Good to know | Integration testing framework cho messaging, HTTP, SOAP, Kafka và enterprise integration. |
| [Assertion](topics/assertion.md) | Personal must know | Kỹ thuật kiểm tra expected vs actual rõ ràng để test failure dễ hiểu. |
| [AssertJ](topics/assertj.md) | Good to know | Fluent assertion library giúp test Java đọc tự nhiên. |
| [Integration Testing](topics/integration-testing.md) | Good to know | Test nhiều layer/dependency phối hợp, ví dụ API + database + message broker. |
| [wiremock](topics/wiremock.md) | Personal must know | Mock HTTP server để test service gọi API ngoài mà không phụ thuộc mạng thật. |
| [E2E Testing](topics/e2e-testing.md) | Good to know | Test end-to-end qua UI/API như người dùng thật, ít nhưng giá trị cho flow quan trọng. |
| [Testcontainers](topics/testcontainers.md) | Personal must know | Chạy database/broker thật trong container cho integration test đáng tin hơn. |
| [Selenium](topics/selenium.md) | Good to know | Browser automation cho UI E2E test. |

### Libraries

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Good to Know Libraries](topics/good-to-know-libraries.md) | Good to know | Các thư viện Java phổ biến nên biết để đọc codebase và tránh tự viết lại bánh xe. |
| [beanvalidation](topics/beanvalidation.md) | Good to know | Jakarta Bean Validation dùng annotation như @NotNull, @Size, @Email để validate DTO/entity. |
| [bouncycastle](topics/bouncycastle.md) | Good to know | Crypto provider/library cho Java khi JDK mặc định không đủ thuật toán/format. |
| [gson](topics/gson.md) | Good to know | JSON serialization/deserialization library của Google; hiện nhiều Spring app mặc định dùng Jackson. |
| [shiro](topics/shiro.md) | Good to know | Apache Shiro là security framework cho authentication/authorization/session. |
| [RxJava](topics/rxjava.md) | Good to know | Reactive programming library dựa trên Observable/Flowable, gặp trong Android/async pipelines. |

### Workflow and Messaging

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Workflow Engine](topics/workflow-engine.md) | Personal must know | Điều phối workflow dài, retry, state, timeout và compensation cho nghiệp vụ phức tạp. |
| [Temporal](topics/temporal.md) | Personal must know | Workflow engine mạnh cho durable execution, retry và long-running business process. |
| [Message-Broker](topics/message-broker.md) | Personal must know | Hệ thống truyền message/event giữa service bất đồng bộ. |
| [RabbitMQ](topics/rabbitmq.md) | Personal must know | Message broker AMQP phổ biến, mạnh về queue/routing patterns. |
| [Apache Kafka](topics/apache-kafka.md) | Good to know | Distributed event streaming platform cho event log, stream processing, data pipelines. |
| [ActiveMQ](topics/activemq.md) | Possibilities | Message broker hỗ trợ JMS, thường gặp trong enterprise Java cũ. |
| [Apache Pulsar](topics/apache-pulsar.md) | Possibilities | Distributed messaging/streaming system tách compute-storage, multi-tenant. |

### MicroServices

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [MicroServices](topics/microservices.md) | Personal must know | Kiến trúc chia hệ thống thành service nhỏ, deploy độc lập, giao tiếp qua API/event. |
| [Message-Bus](topics/message-bus.md) | Good to know | Bus nội bộ để publish/subscribe event trong app hoặc giữa module/service. |
| [mbassador](topics/mbassador.md) | Possibilities | Event bus library cho Java, chủ yếu cần biết nếu gặp codebase dùng nó. |
| [Apollo](topics/apollo.md) | Personal must know | Trong roadmap này có thể ám chỉ config/service framework; cần đọc theo context dự án cụ thể. |
| [micronaut](topics/micronaut.md) | Personal must know | Framework JVM hiện đại cho microservice, DI compile-time, startup nhanh. |
| [RPC](topics/rpc.md) | Personal must know | Remote Procedure Call: gọi method/service từ xa qua protocol chặt chẽ hơn REST trong nhiều hệ internal. |
| [Protocol Buffers](topics/protocol-buffers.md) | Personal must know | Schema language/binary serialization của Google, thường dùng với gRPC. |
| [gRPC-Java](topics/grpc-java.md) | Personal must know | RPC framework hiệu năng cao dùng HTTP/2 + Protobuf, phù hợp service-to-service. |
| [thrift](topics/thrift.md) | Personal must know | RPC/serialization framework của Apache, gặp trong một số hệ phân tán. |

### Scheduling

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Task Scheduling](topics/task-scheduling.md) | Good to know | Chạy job theo thời gian: cron, delayed job, retry, distributed scheduler. |
| [cron-utils](topics/cron-utils.md) | Personal must know | Java library parse/validate/describe cron expression. |
| [Aurora](topics/aurora.md) | Good to know | Apache Aurora là scheduler/service orchestrator; ngày nay ít phổ biến hơn Kubernetes nhưng nên biết lịch sử/context. |

### AI/LLM

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [AI/LLM](topics/ai-llm.md) | Personal must know | Ứng dụng Java với LLM: prompt, tool calling, RAG, vector database, guardrails, observability. |
| [langchain4j](topics/langchain4j.md) | Personal must know | Framework Java để tích hợp LLM, chat memory, tools, embeddings và RAG. |
| [langgraph4j](topics/langgraph4j.md) | Personal must know | Thư viện/port theo hướng graph workflow cho agent/LLM orchestration trong Java. |

### Java Patterns

| Chủ đề | Mức | Học để làm gì |
|---|---|---|
| [Java Patterns](topics/java-patterns.md) | Personal must know | Design patterns và concurrency patterns giúp đặt tên giải pháp, không phải công thức dùng mù quáng. |
| [Creational](topics/creational.md) | Good to know | Nhóm pattern tạo object: Factory, Builder, Singleton, Prototype. |
| [Structural](topics/structural.md) | Good to know | Nhóm pattern cấu trúc object/class: Adapter, Decorator, Facade, Proxy, Composite. |
| [Behavioral](topics/behavioral.md) | Good to know | Nhóm pattern hành vi: Strategy, Observer, Command, Template Method, Chain of Responsibility. |
| [synchronization](topics/synchronization.md) | Good to know | Kỹ thuật đồng bộ truy cập shared state bằng synchronized, locks, atomic classes. |
| [Concurrency](topics/concurrency.md) | Good to know | Pattern xử lý đồng thời: executor, producer-consumer, futures, structured concurrency. |
| [Messaging](topics/messaging.md) | Good to know | Pattern messaging: queue, pub/sub, request-reply, outbox, idempotent consumer. |
| [Stability](topics/stability.md) | Good to know | Pattern tăng độ ổn định: timeout, retry, circuit breaker, bulkhead, fallback. |
| [Lock](topics/lock.md) | Good to know | Lock trong local JVM và distributed system, dùng cẩn thận để tránh deadlock/race condition. |


## Project tổng hợp nên làm

Xây app **Student Enrollment Platform**:

- REST API: quản lý sinh viên, môn học, đăng ký môn.
- Database: PostgreSQL, migration bằng Flyway hoặc Liquibase.
- ORM: Hibernate/JPA.
- Cache: Caffeine cho course lookup, Redis nếu chạy nhiều instance.
- Messaging: publish event `StudentEnrolled`.
- Testing: JUnit, AssertJ, Mockito, Testcontainers, WireMock.
- Logging: structured logs có request id.
- Security: JWT/OAuth2 basic flow.
- Optional AI: hỏi đáp tài liệu môn học bằng RAG + vector database.

## Nguồn tra cứu chính

- OpenJDK JDK 25: https://openjdk.org/projects/jdk/25/
- JDK 26 Release Notes: https://jdk.java.net/26/release-notes
- Oracle Java SE Support Roadmap: https://www.oracle.com/java/technologies/java-se-support-roadmap.html
- Spring Boot: https://spring.io/projects/spring-boot
- Maven: https://maven.apache.org/
- Gradle: https://gradle.org/
- JUnit 5: https://junit.org/junit5/
- Testcontainers: https://testcontainers.com/

## Tài liệu phụ trong folder này

- [Lộ trình học theo tuần](learning-plan.md)
- [Project tổng hợp chi tiết](student-enrollment-platform.md)
