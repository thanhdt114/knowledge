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
Trong cột Example: giả sử list có kiểu dữ liệu là List (khác Stream)
| Method | Type return | Description | Example |
| --- | --- | --- | --- |
| `count()` | long | Trả về số lượng phần từ của danh sách | `list.stream().count(); ` |
| `distinct()` | Stream\<T\> | Loại bỏ các phần tử trùng nhau | `list.stream().distinct();` |
| `filter(Predicate<? super T> predicate)` | Stream\<T\> | Lọc dữ liệu dựa trên điều kiện (thường là so sánh) | `list.stream().filter(item -> item == "Thanh");` |
| `forEach(Consumer<? super T> action)` | void | Duyệt qua toàn bộ phần tử | `list.stream().forEach(item -> {System.out.print(item + " \| ");});` |
| `limit(long maxSize)` | Stream\<T\> | Lấy các phần tử từ 0 đến n - 1 | `list.stream().limit(2);` |
| `map(Function<? super T,? extends R> mapper)` | Stream\<T\> | Thực hiện thao tác trên toàn bộ phần tử dựa trên biểu thức (thường là tính toán thêm hoặc thay đổi phần tử)| `list.stream().map(item -> item += "DepTrai")` |
| `max(Comparator<? super T> comparator)` | Optional\<T\> | Tìm giá trị lớn nhât | `list.stream().max(Comparator.comparingInt(String::length)).get()` |
| `min(Comparator<? super T> comparator)` | Optional\<T\> | Tìm giá trị nhỏ nhất | `list.stream().min(Comparator.comparingInt(String::length)).get()` |
| `skip(long n)` | Stream\<T\> | Lấy các phần tử từ n - 1 đến hết| `list.stream().skip(2)` |
| `	sorted()` | Stream\<T\> | Sắp xếp các phần tử theo thứ tự nhất định | `list.stream().sorted()` |

## Code Examples
```java
import java.util.ArrayList;
import java.util.Comparator;
import java.util.List;

public class test {
	public static void main(String[] args) {
        List<String> list = new ArrayList<String>();
        
        list.add("Thanh");
        list.add("Dam");
        list.add("Duy");
        list.add("Duy");
        list.add("Tien");
        
        System.out.print("Stream demo: ");
        list.stream().forEach(item -> {System.out.print(item + " | ");});
        
        System.out.println("\nCount: " + list.stream().count());
        
        System.out.print("Distinct: ");
        list.stream().distinct().forEach(item -> {
        	System.out.print(item + " | ");
        });
        
        System.out.print("\nFilter: ");
        list.stream().filter(item -> item == "Thanh").forEach(item -> {
        	System.out.print(item + " | ");
        });
        
        System.out.print("\nSort: ");
        list.stream().sorted().forEach(item -> {
        	System.out.print(item + " | ");
        });
        
        System.out.print("\nForEach: ");
        list.stream().forEach(item -> {System.out.print(item + " | ");});
        
        System.out.print("\nLimit: ");
        list.stream().limit(2).forEach(item -> {System.out.print(item + " | ");});
        
        System.out.print("\nMap: ");
        list.stream().map(item -> item += "DepTrai").forEach(item -> {System.out.print(item + " | ");});
        
        System.out.println("\nMax: " +  list.stream().max(Comparator.comparingInt(String::length)).get());
       
        System.out.println("Min: " +  list.stream().min(Comparator.comparingInt(String::length)).get());
        
        System.out.print("Skip: ");
        list.stream().skip(2).forEach(item -> {System.out.print(item + " | ");});
        
        System.out.print("\nSorted: ");
        list.stream().sorted().forEach(item -> {System.out.print(item + " | ");});
    }
}
```
Kết quả
```
Stream demo: Thanh | Dam | Duy | Duy | Tien | 
Count: 5
Distinct: Thanh | Dam | Duy | Tien | 
Filter: Thanh | 
Sort: Dam | Duy | Duy | Thanh | Tien | 
ForEach: Thanh | Dam | Duy | Duy | Tien | 
Limit: Thanh | Dam | 
Map: ThanhDepTrai | DamDepTrai | DuyDepTrai | DuyDepTrai | TienDepTrai | 
Max: Thanh
Min: Dam
Skip: Duy | Duy | Tien | 
Sorted: Dam | Duy | Duy | Thanh | Tien | 
```

## Note
### Convert Stream to List
- Khi gọi hàm stream thì List được gọi đã được convert thành 1 stream, để convert ngươc lại từ 1 stream thành List ta dùng hàm `stream().toList()` 
```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

List<Integer> list = new ArrayList<Integer>();
list.stream().toList();

Stream<String> stream = Stream.empty();
list = stream.toList();
```