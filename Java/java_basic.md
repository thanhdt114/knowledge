# Statement Java

## 1. Print to the screen

Trong java sử dụng câu lệnh sau để in thông tin ra màn hình: `System.out.println("Hello, World!");`

```java
public class HelloWorld
{
    public static void main(String[] args)
    {
        System.out.print("Hello, World!");      
        // print on 1 line (if you continue to print, you will continue to write on the current line)

        System.out.println("Hello, World!");    
        // print on 1 line (if println continues, print on the new line just below)
    }
}
```

## 2. Comment in java

Trong java hỗ trợ comment 1 dòng hoặc comment nhiều dòng bằng 2 câu lệnh sau

-   Comment 1 dòng: `// Your comment`, có thể comment ngay phía sau câu lệnh
-   Comment nhiều dòng: `/* Your comment */`

## 3. Variables in java

### Các kiểu biến phổ biến trong java

-   String : dùng để lưu các giá trị chuỗi ví dụ như tên sinh viên là Nguyễn Văn A
-   int : dùng để lưu các giá trị số ví dụ như số điện thoại 0903049583
-   float : dùng để lưu các giá trị số thập phân như tiền tệ 1.000.500 VND
-   char : dùng để lưu 1 ký tự ví dụ ký tự a hoặc b
-   boolean : dùng để lưu giá trị đúng hay sai.

### Ép kiểu trong java
Giả sử:
- a: Integer
- b: Double
- s: String

Thực hiện ép kiểu cho 3 kiểu dữ liệu phổ biến trên:

- Number to Number: `int a = (int)(b)`
- Number to String: `String s = String.valueOf(a)`
- String to Number: `int a = Integer.parseInt(a)`

```java
System.out.println("Convert Data Type");

int a = 10;
double b = 20;
String s = "30";

System.out.println("a = " + a);
System.out.println("b = " + b);
System.out.println("s = " + s);

b = 99;
a = (int)(b);
System.out.println("Number to Number: a = " + a);

a = 88;
s = String.valueOf(a);
System.out.println("Number to String: s = " + s);

s = "77";
a = Integer.parseInt(s);
System.out.println("String to number: a = " + a);
```
Kết quả: 
```
Convert Data Type
a = 10
b = 20.0
s = 30
Number to Number: a = 99
Number to String: s = 88
String to number: a = 77
```

### Note 3

Khi khai báo biến trong java phải gán giá trị ban đầu, nếu không gán giá trị mà chạy chương trình thì sẽ thông báo lỗi.
Ví dụ

-   Code đúng

```java
String name = “Tran Tuan Thanh”;
System.out.println(name);
```

-   Code sai

```java
String name;
System.out.println(name);
```

Khi thực hiện nhân 2 số lớn có kiểu integer, kết quả trả về sẽ là 1 số integer có kiểu dữ liệu là kiểu dữ liệu có range lớn nhất trong 2 số nhân vào nhau.

Ví dụ: các đoạn code sau cho kết quả giống nhau

```java
long a = 384847522;
long b = 988347273;

System.out.println(a * b); // Result: 380362998889507506
```

```java
int a = 384847522;
long b = 988347273;

System.out.println(a * b); // Result: 380362998889507506
```

Code chạy kết quả sai

```java
int a = 384847522;
int b = 988347273;

System.out.println(a * b); // Result: -628954446
```

## 4. Input/Output data

### Input

Sử dụng Scanner package. \
Khai báo package: `import java.util.Scanner;` \
Khởi tạo Scanner: `Scanner sc = new Scanner(System.in);` \
Sử dụng Scanner:

-   String (không bao gồm khoảng trắng): `String s = sc.next();`
-   Không phải String: `int a = sc.nextInt();`
-   String (bao gồm khoảng trắng): `String s = sc.nextLine();` (trước khi dùng câu lệnh này phải gọi `sc.nextLine()` để đọc hết ký tự dư thừa còn sót lại trước đó)
-   char (lấy ký tự đầu tiên trong chữ đầu tiên): `char c = sc.next().charAt(0);`

Code mẫu

```java
import java.util.Scanner;

public class Input {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        sc.nextLine();
        String name = sc.nextLine();
        String s = sc.next();
        int a = sc.nextInt();
        char c = sc.next().charAt(0);

        // Enter value:
        /*
            Tran Tuan Thanh
            x
            10
            hello
        */

        System.out.println(name); // output: Tran Tuan Thanh
        System.out.println(s); // output: x
        System.out.println(a); // output: 10
        System.out.println(c); // output: h
    }
}
```

## 5. Compare operators

### Các toán tử so sánh trong java

| Syntax | Description               | Example  |
| ------ | ------------------------- | -------- |
| ==     | So sánh bằng              | `a == b` |
| !=     | So sánh khác              | `a != b` |
| >      | So sánh lớn hơn           | `a > b`  |
| <      | So sánh bé hơn            | `a < b`  |
| >=     | So sánh lơn hơn hoặc bằng | `a >= b` |
| <=     | So sánh bé hơn hoặc bằng  | `a <= b` |

#### Note: so sánh 2 String

Dùng method `equals()` để so sánh 2 String

```java
String a = "Tran Tuan Thanh";
String b = "Tran Tuan Thanh";

if (a.equals(b)) {
    System.out.println("a equal to b");
}
// output: a equal to b
```

### Các toán tử logic trong java

trong ví dụ ta giả sử

-   a = true
-   b = true
-   c = false
-   d = false

| Syntax | Description                                        | Example           |
| ------ | -------------------------------------------------- | ----------------- |
| &&     | AND: Trả về true khi 2 vế đều là true              | `a && b` => true  |
| \|\|   | OR: Trả về false khi 2 vế đều là false             | `c \|\| d` => false |
| !      | NOT: Lấy phủ định                                  | `!a` => false     |
| ^      | XOR: trả về false khi 2 vế giống nhau và ngược lại | `a ^ b` => false  |

## 6. Loop statements
### For
Sử dụng vòng lặp For để tạo vòng lặp chạy từ i = 0 đến i = 10

```java
for (int i = 0; i <= 10; i++) {
    System.out.print(i + " ");
}
```

### ForEach
Sử dụng vòng lặp ForEach để tạo vòng lặp chạy qua toàn bộ phần tử mà không cần biết kích thước

```java
System.out.println("ForEach Demo");

List<Integer> list = new ArrayList<Integer>();

list.add(1);
list.add(2);
list.add(3);

for (Integer item : list) {
    System.out.print(item + " | ");
}
```
Kết quả
```
ForEach Demo
1 | 2 | 3 | 
```

### While
Sử dụng vòng lặp While để tạo vòng lạp chạy cho tới khi điều kiện của vòng lặp bị sai
```java
int n = 0;
while (n <= 10) {
    System.out.print(n + " ");
    n++;
}
```

### Do-While
Sử dụng vòng lặp Do-While để tạo vòng lạp chạy cho tới khi điều kiện của vòng lặp bị sai\
Khác nhau giữa Do-While và while là Do-While sẽ thực hiện đoan code bên trong do trước rồi mới đi kiểm tra điều kiện và cứ thế lặp lại
```java
int i = 1;
do {
    System.out.print(i + " ");
    i++;
} while (i <= 5);
```

### Note
Sử dụng break và continue
- `break;` thoát vòng lặp hiện tại
- `continue;` bỏ qua đoạn code bên dưới continue và đi đến lần lặp tiếp theo

## 7. Array
### Mảng trong java
Bắt buộc phải khai báo độ lớn (size) của mảng
```java
int[] array = new int[10];

for (int i = 0; i < 10; i++) {
    array[i] = sc.nextInt();
}
```
### Note: Nên dùng ArrayList thay cho Array

