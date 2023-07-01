# ARRAY HANDLE

# 1. List
## Khái nhiệm
- List là 1 interface trong java dùng để lưu trữ danh sách có thứ tự 
- Sử dụng thư viện `java.util.List`
## Methods

| Method | Type return | Description | Example |
| --- | --- | --- | --- |
| `add(int index, E element)` | void | Chèn phần tử vào vị trí chỉ định | `list.add(1, "Thanh"); ` |
| `add(E e)` | boolean | Thêm phần tử vào cuối | `list.add("Thanh");` |
| `get(int index)` | E | Lấy giá trị tại vị trí chỉ định | `list.get(1);` |
| `set(int index, E element)` | E | Gán giá trị tại vị trí chỉ định | `list.set(1, "Thanh")` |
| `remove(int index)` | E | Xóa phần tử tại ví trí chỉ định | `list.remove(1);` |
| `isEmpty()` | boolean | Kiểm tra trống  | `list.isEmpty();` |
| `indexOf(Object o)`  | int | Tìm vị trí đầu tiên của phần tử (hoặc trả về -1) | `list.indexOf("Thanh");` |
| `sort(Comparator<? super E> c) ` | void | Sắp xếp các phần tử theo sự so sánh | `list.sort();` |
| `size()` | int | Lấy số phần tử | `list.size();` |
| `clear()` | void | Xóa tất cả phần tử | `list.clear();` |

## Code Example
```java
import java.util.ArrayList;
import java.util.List;

public class test {
	public static void main(String[] args) {
		System.out.println("List demo");
		
        List<String> list = new ArrayList<String>();
        
        list.add("Tien");
        list.add("Dam");
        list.add("Khoi");
        System.out.println("add: " + list);

        list.add(2, "Thanh");
        System.out.println("add: " + list);

        System.out.println("get: " + list.get(2));

        list.set(3, "ThanhDepTrai");
        System.out.println("set: " + list);

        list.remove(1);
        System.out.println("remove: " + list);

        System.out.println("Is Empty: " + list.isEmpty());

        System.out.println("Index Of: " + list.indexOf("Thanh"));

        list.sort(null);
        System.out.println("Size: " + list.size());
        
        list.clear();
        System.out.println("Clear: " + list);
    }
}
```
Kết quả: 
```
List demo
add: [Tien, Dam, Khoi]
add: [Tien, Dam, Thanh, Khoi]
get: Thanh
set: [Tien, Dam, Thanh, ThanhDepTrai]
remove: [Tien, Thanh, ThanhDepTrai]
Is Empty: false
Index Of: 1
Size: 3
Clear: []
```

# 2. ArrayList
## Khái nhiệm
- ArrayList là 1 danh sách các phần tử theo thứ tự, ArrayList được xem là con của List 
- Sử dụng thư viện `java.util.ArrayList`
## Methods
Các phương thức của ArrayList tương tự như List

# 3. Stream
## Khái niệm
- Stream được sử dụng để xử lý dữ liệu như duyệt, tìm giá trị lớn (bé) nhất, sorting, filter, hay limit. 
- Dùng Stream sẽ thực hiện duyệt qua dữ liệu kết hợp xử lý mà không làm thay đổi dữ liệu gốc

## Methods
| Method | Type return | Description | Example |
| --- | --- | --- | --- |
| `count()` | long | Trả về số lượng phần từ của danh sách | `list.stream().count(); ` |
| `distinct()` | Object | Loại bỏ các phần tử trùng nhau | `list.stream().distinct();` |
| `filter(Predicate<? super T> predicate)` | Object | Lọc dữ liệu | `list.stream().filter(item -> item == "Thanh");` |
| `forEach(Consumer<? super T> action)` | void | Duyệt qua toàn bộ phần tử | `list.stream().forEach(item -> {System.out.print(item + " \| ");});` |
| `` |  |  | `` |
| `` |  |  | `` |
| `` |  |  | `` |
| `` |  |  | `` |
| `` |  |  | `` |
| `` |  |  | `` |

## Code Examples

## Note
### Convert Stream to List
- Khi gọi hàm stream thì List được gọi đã được convert thành 1 stream, để convert ngươc lại từ 1 stream thành List ta dùng hàm `collect(Collectors.toList())` 
- Sử dụng thư viện `java.util.stream.Collectors`
```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

List<Integer> list = new ArrayList<Integer>();
list.stream().collect(Collectors.toList());

Stream<String> stream = Stream.empty();
list = stream.collect(Collectors.toList());
```