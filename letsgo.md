-- Design pattern

-> Design pattern là khái niệm để nói về các mô hình, kiến trúc, các kiểu thiết kế phần mềm hoặc hệ thống.

-> Có 3 loại design pattern phổ biến

--- Creational: Bao gồm những loại patterns cung cấp solutions để tạo ra các object 1 cách linh hoạt.

---- Singleton

---- Factory Method: Factory method cung cấp interface mà trong đó định nghĩa các methods cho việc tạo ra các object nhưng nó cho phép các subclasses ( lớp con ) có thể thay đổi type của object mà nó tạo ra theo các business logic cụ thể.

Cấu trúc của một Factory Method:

- Super Class: 1 Super Class trong Factory Method có thể là 1 interface hay đơn giản là 1 class thông thường.
- Sub Classes: Các class con mà implement các methods của Super Class với các tham số khác nhau theo từng nghiệp vụ của nó.
- Factory Class: 1 Class chịu trách nghiệm khởi tạo các object dựa theo params ( các tham số đầu vào ). Class này sẽ cung cấp 1 method dành cho việc khởi tạo và truy xuất object.

VD: Giả sử chúng ta có 1 ứng dụng quản lý giao thông. Nhưng ứng dụng đó chỉ có thể tạo ra các object từ class Car dẫn đến việc ứng dụng của chúng ta chỉ có thể handle các request từ đường bộ. Nhưng sau đó khách hàng muốn ứng dụng chúng ta handle thêm các request từ đường biển. Nếu như dùng if else mỗi lần tạo ra các object mới thì sẽ bị tình trạng lặp code và không linh hoạt.

---- Abstract Factory

---- Builder

---- Prototype

-- C#

-> C# là gì ?

--- C# là một ngôn ngữ lập trình hướng đối tượng bậc cao do microsoft tạo ra.
--- C# là một ngôn ngữ biên dịch, nó được convert sang bytecode trên máy ảo CLR ( Common Language Runtime ). Rồi sau đó mới chuyển sang mã máy.
--- Các biến của C# có thể được phân loại theo vị trí của bộ nhớ.

--- Có 3 kiểu dữ liệu trong C#

- Values Types ( Kiểu giá trị ): Là kiểu giá trị mà được lưu trữ dưới dạng value trong bộ nhớ. Có nghĩa là biến đó lưu trữ trực tiếp giá trị được gán ( Bool, byte, char, decimal, double, Enum, float, int, long, short and struct ).

- Reference Types ( Kiểu tham chiếu ): Không giống như kiểu giá trị, kiểu tham chiếu không lưu trữ trực tiếp giá trị của nó. Thay vào đó, nó lưu trữ địa chỉ nơi mà giá trị được giữ trong bộ nhớ. Giống như nó đang lưu trữ một con trỏ trỏ đến địa chỉ nơi biến được lưu trữ ( String, arrays, classes and delegate ).

  --> Trong đó, Array là một tập hợp các giá trị có cùng kiểu dữ liệu được lưu trữ tại các vị trí liền kề nhau trong bộ nhớ.

- Pointer Types ( Kiểu con trỏ ): Nhằm mục đích lưu trữ địa chỉ của 1 con trỏ khác.

--- Có 4 loại toán tử trong C#

- Toán tử số học: ( + - nhân / % ++ -- )
- Toán tử gán: ( = += -= nhân= /= %= &= )
- Toán tử so sánh: ( == != >= <= > < )
- Toán tử logic: ( && || ! )

--- Có 4 kiểu class trong C#

- static class: Những class này không thể tạo ra các instance ( object ). Khi khai báo 1 static class thì tất cả biến, hàm trong class cũng phải là static.

- partial class:

- abstract class:

- sealed class: Lớp này không thể được kế thừa

--- Collection trong C#

- Những class mà dùng để chứa ( storage ) và truy xuất ( retrieval ) dữ liệu được gọi là các collection classes. Những class này hỗ trợ các cấu trúc dữ liệu như stacks, queues, lists, hash tables.

- Những collection classes có vai trò như cấp phát động ( dynamic allocating ) bộ nhớ cho các instances hoặc truy cập vào list các item bằng index hoặc key ( trong khi array chỉ có thể truy cập vào element bằng index ).

- Có 2 dạng Collection Classes là Non-generic và Generic

- Đặc điểm của Collection:

--> Các collection classes nằm trong System.Collections.

--> Collection trong C# cũng được support các methods được tích hợp sẵn như: sắp xếp, thêm, xóa, ...

--> Không cần khai báo kích thước cụ thể khi khởi tạo.

--> Tăng giảm số lượng phần tử 1 cách linh hoạt.

--> Lưu trữ được nhiều phần tử thuộc nhiều type khác nhau.

- 1 số các collection classes

--> ArrayList:

- Về bản chất giống như Array nhưng khi khai báo 1 Array phải thiết lập kích cỡ tính -> bộ nhớ là cố định trong khi với ArrayList kích cỡ có thể tăng giảm tùy ý.

- Kiểu dữ liệu của các elements trong Array bắt buộc phải giống nhau trong khi ArrayList có thể chứa nhiều kiểu dữ liệu.

- Kiểu dữ liệu đầu vào của ArrayList là object. Mỗi dữ liệu truyền vào luôn bị convert sang object trước khi đưa vào ArrayList.

- ArrayList chấp nhận giá trị null trong khi Array thì không. Thêm nữa, ArrayList hỗ trợ sẵn các methods và thuộc tính có sẵn như count, add() - thêm value vào cuối list, capacity(), remove() - xóa phần tử đầu tiên xuất hiện trong list ...

--> Hashtable:

- Là 1 collection lưu trữ data dưới dạng key-value và chỉ có thể được truy xuất bởi key.

- Hashtable không có các index.

- Mỗi phần từ trong Hashtable bao gồm 1 cặp key-value được C# định nghĩa là 1 DictionaryEntry.

- Có các methods và thuộc tính hỗ trợ: count, Add(), ContainsKey(), ContainsValue(), ...

--> SortedList:

- Là sự kết hợp giữa ArrayList và HashTable nên cũng được hỗ trợ các methods và thuộc tính giống như 2 collection classes đó.

- Giống như Hashtable, SortedList cũng là một collection chứa các phần tử dưới dạng key-value. Nhưng các phần tử sẽ được sắp xếp theo key. Việc sắp xếp đó sẽ được tự động mỗi khi thêm 1 phần tử khác vào.

- Có thể truy xuất giá trị từ key lẫn index.

--> Stack:

- Trong C# thì Stack là 1 collection và là 1 kiểu cấu trúc dữ liệu hoạt động theo cơ chế ( LIFO - Last In First Out ). Nó không thể truy xuất phần tử theo index.

- Thêm phần tử gọi là Push ( Đẩy vào ), Lấy phần tử gọi là Pop ( Đẩy ra - lấy phần tử được thêm vào cuối cùng ).

- Được hỗ trợ các methods như:

Peek() - Trả về phần tử trên cùng trong Stack.

Pop() - Trả về phần tử trên cùng trong Stack và xóa phần tử đó khỏi Stack.

Push(object Value) - Thêm 1 phần tử vào đầu Stack. Và còn nhiều methods khác ...

--> Queue:

- Trong C# thì Queue là 1 collection và là 1 kiểu cấu trúc dữ liệu hoạt động theo cơ chế ( FIFO - First In First Out ). Là 1 danh sách lưu trữ các đối tượng nhưng không thể truy xuất các đối tượng đó theo index.

- Thêm phần tử vào Queue gọi là Enqueue ( xếp hàng ), Lấy phần tử ra khỏi Queue gọi Dequeue ( ra khỏi hàng ) và luôn luôn lấy phần tử được thêm vào đầu tiên.

- Hỗ trợ các methods như Enqueue(), Dequeue(), so on and so forth

--> BitArray:

- Trong C# BitArray là 1 collection lưu trữ các phần tử dưới dạng các bit ( 0 và 1 ) và được biểu diễn như kiểu Boolean. Trong đó true là 1 bit và false là 0 bit. Giá trị mặc định của các phần tử BitArray là false.

- Nên dùng BitArray thay cho các đổi tượng kiểu bool là vì mỗi phần tử trong BitArray chỉ tốn 1 bit, trong khi kiểu bool chỉ lưu 2 giá trị là true hoặc false nhưng lại tốn đến 1 bytes cho mỗi biến.

--> List:

- List là 1 Generic Collection, là sự kết hợp giữa ArrayList và Generic.

- Không như ArrayList, List là Collection Class bắt buộc phải chỉ định kiểu đầu vào khi muốn tạo 1 instance.

--> Dictionary

- Dictionary là 1 Generic Collecion, là sự kết hợp giữa Hashtable và Generic

--- Generic trong C#

- Generic trong C# là một tính năng trong C#. Trong đó kiểu dữ liệu ( của biến, tham số, kiểu trả về của các methods ) được xác định ở giai tạo khởi tạo.

- Generic allow to define generic classes, interface, abstract classes, fields, methods, events, delegates using Type Parameter without specific data type. A type parameter is a placeholder for paritucal type specified ( type được chỉ định cụ thể ) when create an instance of the generic type.
