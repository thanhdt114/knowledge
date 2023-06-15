# Statement Java

## 1. Print to the screen
Trong java sử dụng câu lệnh sau để in thông tin ra màn hình: `System.out.println("Hello, World!");`
```java
public class HelloWorld 
{
   public static void main(String[] args) 
   {
	System.out.println("Hello, World!");
   }
}
```

## 2. Comment in java
Trong java hỗ trợ comment 1 dòng hoặc comment nhiều dòng bằng 2 câu lệnh sau
- Comment 1 dòng: `// Your comment`, có thể comment ngay phía sau câu lệnh
- Comment nhiều dòng: `/* Your comment */`

## 3. Variables in java
Các kiểu biến phổ biến trong java
- String : dùng để lưu các giá trị chuỗi ví dụ như tên sinh viên là Nguyễn Văn A
- int : dùng để lưu các giá trị số ví dụ như số điện thoại 0903049583
- float : dùng để lưu các giá trị số thập phân như tiền tệ 1.000.500 VND
- char : dùng để lưu 1 ký tự ví dụ ký tự a hoặc b
- boolean : dùng để lưu giá trị đúng hay sai.

Khi khai báo biến trong java phải gán giá trị ban đầu, nếu không gán giá trị mà chạy chương trình thì sẽ thông báo lỗi.
Ví dụ
- Code đúng
```java
String name = “Tran Tuan Thanh”;
System.out.println(name);
```
- Code sai
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
