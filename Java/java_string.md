# JAVA STRING
## 1. String methods

| Method | Return type | Meaning | Example |
| --- | --- | --- | --- |
| `charAt()` | char | Lấy ký tự tại vị trí chỉ định | `s.charAt(2)` |
| `codePointAt()` | int | Lấy mã Unicode của ký tự tại vị trí chỉ định | `s.codePointAt(2)` |
| `concat()` | String | Nối chuỗi (không làm thay đổi chuỗi ban đầu) | `s.concat("dep trai")` |
| `contains()` | boolean | Kiểm tra chuỗi con có tồn tại hay không | `s.contains("Thanh")` |
| `equals()` | boolean | So sánh 2 chuỗi | `s.equals("Thanh")` |
| `hashCode()` | int | Mã hóa chuỗi | `s.hashCode()` |
| `indexOf()` | int | Tìm chuỗi con đầu tiên | `s.indexOf("Tuan")` |
| `isEmpty()` | boolean | Kiểm tra chuỗi rỗng | `s.isEmpty()` |
| `length()` | int | Lấy kích thước chuỗi | `s.length()` |
| `replace()` | String | Thay thế ký tự trong chuỗi | `s.replace("a", "e")` |
| `split()` | String[] | Cắt chuỗi, ngắn cách bằng chuỗi con | `s.split(" ")` |
| `toCharArray()` | char[] | Convert String thành mảng char theo thứ tự String ban đầu | `s.toCharArray()` |
| `toLowerCase()` | String | Chuyển chuỗi thành ghi  thường toàn bộ | `s.toLowerCase()` |
| `toUpperCase()` | String | Chuyển chuỗi thành ghi hoa toàn bộ | `s.toUpperCase()` |
| `trim()` | String | Loại bỏ khoảng trắng ở 2 đầu của chuỗi | `s.trim()` |
| `valueOf()` | String | Convert data khác thành kiểu String | `String.valueOf(char c)` |

### Code Example
```java
public class test3 {
	public static void main(String[] args) {
		String s = "  Tran Tuan Thanh  ";
		System.out.println("String method Demo: " + s);

		System.out.println("charAt: " + s.charAt(3 - 1));
		
		System.out.println("codePointAt: " + s.codePointAt(3 - 1));
		
		System.out.println("concat: " + s.concat(" dep trai"));
		
		System.out.println("contains: " + s.contains("Tuan"));
		
		System.out.println("equals: " + s.equals("Tran Tuan Thanh"));
		
		System.out.println("hashCode: " + s.hashCode());
		
		System.out.println("indexOf: " + s.indexOf("Tuan"));
		
		System.out.println("isEmpty: " + s.isEmpty());
		
		System.out.println("length: " + s.length());
		
		System.out.println("replace: " + s.replace("a", "e"));
		
		for (String item : s.split(" ")) {
			System.out.println("split: " + item);
		}
		
		System.out.println("toCharArray: " + s.toCharArray()[0]);
		
		System.out.println("toLowerCase: " + s.toLowerCase());
		
		System.out.println("toUpperCase: " + s.toUpperCase());
		
		System.out.println("trim: " + s.trim());

        System.out.println("valueOf: " + String.valueOf(s.charAt(3)));
	}	
}
```
Kết quả
```
String method Demo:   Tran Tuan Thanh  
charAt: T
codePointAt: 84
concat:   Tran Tuan Thanh   dep trai
contains: true
equals: false
hashCode: 46783530
indexOf: 7
isEmpty: false
length: 19
replace:   Tren Tuen Thenh  
split: 
split: 
split: Tran
split: Tuan
split: Thanh
toCharArray:  
toLowerCase:   tran tuan thanh  
toUpperCase:   TRAN TUAN THANH  
trim: Tran Tuan Thanh
valueOf: r
```