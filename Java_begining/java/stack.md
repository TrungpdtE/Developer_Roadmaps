# Stack

> Nhóm: Collections

## Mục tiêu

- Hiểu LIFO.
- Biết push/pop/peek.
- Dùng stack cho undo, parsing, DFS.

## Lý thuyết dễ hiểu

Stack giống chồng đĩa: đặt lên trên và lấy từ trên. Rất hữu ích cho thuật toán, undo history, kiểm tra ngoặc.

## Facts cần nhớ

- LIFO nghĩa là vào sau ra trước.
- Trong Java mới, dùng Deque thay `java.util.Stack` trong nhiều trường hợp.
- Stack overflow có thể xảy ra với recursion quá sâu.

## Code mẫu

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class StackDemo {
    public static boolean hasBalancedParentheses(String text) {
        Deque<Character> stack = new ArrayDeque<>();
        for (char character : text.toCharArray()) {
            if (character == '(') {
                stack.push(character);
            } else if (character == ')') {
                if (stack.isEmpty()) {
                    return false;
                }
                stack.pop();
            }
        }
        return stack.isEmpty();
    }
}
```

## Cách triển khai thực tế

- Dùng stack cho DFS iterative.
- Dùng stack để validate expression.
- Đặt tên rõ nếu dùng Deque như stack.

## Lỗi hay gặp

- Pop khi rỗng.
- Dùng recursion sâu không kiểm soát.
- Nhầm queue và stack.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
