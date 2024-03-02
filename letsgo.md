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

- static class: 1 Class được xác định là static là class tĩnh, không thể tạo các object từ class đó, khi khai báo 1 static class thì yêu cầu tất cả các thuộc tính lẫn methods trong class đó cũng phải static. Static Class dùng để lưu các thông tin dùng chung cho toàn bộ app của chúng ta.

- partial class: partial class cho phép các method và thuộc tính của nó phân chia hoặc chia sẻ qua các file (.cs)

- abstract class: Abstract có nghĩa là "dở dang, chưa hoàn thiện" -> không thể tạo các instances từ Abstract Class. Nếu trong app của chúng ta có quá nhiều Class giống nhau về thuộc tính hay method nào đó thì ta có thể tạo ra 1 Abstract Class cung cấp Abstract method để cho các Class kia có thể kế thừa và ghi đè lại Abstract Method đó để giải quyết vấn đề. ( Abstract methods tên là TinhDienTich thuộc Abstract Shape - Các Class con kế thừa Class Shape có thể override lại phương thức TinhDienTich để tính toán ).

- sealed class: Lớp này không thể được kế thừa

--- Từ khóa Static

- Static Class: 1 Class được xác định là static là class tĩnh, không thể tạo các object từ class đó, khi khai báo 1 static class thì yêu cầu tất cả các thuộc tính lẫn methods trong class đó cũng phải static. Static Class dùng để lưu các thông tin dùng chung cho toàn bộ app của chúng ta.

- Static cho thuộc tính ( properties ) và phương thức ( methods ): Hàm và biến static không thuộc về object mà thuộc về Class, chúng có thể được truy cập trực tiếp từ Class mà không cần tạo ra các instances.

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

- Trong C# thì dữ liệu trong Dictionary có kiểu KeyValuePair<TKey,TValue> tương tự như DictionaryEntry của Hashtable

- So sánh Hashtable và Dictionary

Hashtable: Threadsafe, Hỗ trợ multi threading ko đụng độ tài nguyên, Cặp key-value lưu kiểu object, Dùng cho dữ liệu lớn, Các phần tử được sắp xếp theo key mỗi lần thêm hoặc xóa, Tìm kiếm nhanh hơn Dictionary.

Dictionary: Không hỗ trợ multi threading, Định nghĩa kiểu của key-value lúc khai báo, Không hiệu quả cho dữ liệu lớn, Các phần tử nằm theo thứ tự được thêm vào ( Mỗi khi thêm phần tử là thêm vào cuối ), Tìm kiếm chậm hơn Hastable

--- Generic trong C#

- Generic trong C# là một tính năng trong C#. Trong đó kiểu dữ liệu ( của biến, tham số, kiểu trả về của các methods ) được xác định ở giai tạo khởi tạo.

- Generic allow to define generic classes, interface, abstract classes, fields, methods, events, delegates using Type Parameter without specific data type. A type parameter is a placeholder for paritucal type specified ( type được chỉ định cụ thể ) when create an instance of the generic type.

--- Delegate trong C#

- Delegate trong C# là một kiểu dữ liệu đặc biệt để khai báo biến tham chiếu trỏ tới địa chỉ các hàm hoặc methods. Với điều kiện là các hàm và methods đó có cùng kiểu dữ liệu trả và cùng kiểu dữ liệu tham số đầu vào.

- Một biến delegate có thể gọi nhiều function liên tiếp gọi là multicast. Những functions đó được implment 1 cách tuần tự.

- Dùng delegate khi ta có 1 function, ta muốn 1 biến tham chiếu tới function để có thể dùng biến đó đóng vai trò làm 1 tham số của 1 function khác ( tương tự như callback ).

- Predicate ( Predicate<T in> ): Predicate tương tự như 1 delegate với kiểu trả về là bool. Predicate chỉ có thể nhận vào 1 params duy nhất.

- Action ( Action<T in1, T in2, ...> ): Action tương tự như 1 delegate với kiểu trả về là void. Với in1, int2 là tham số nhận vào.

--- Event trong C#

- Event trong C# là 1 kiểu multicast delegate đặc biệt chỉ có thể được gọi trong class hoặc struct nơi mà nó được khai báo.

- Event dựa trên delegate model, trong khi delegate model dựa trên Observer Design Pattern.

- 1 biến event nhận về 2 đối số: tham số đầu tiên là object chứa event đó, tham số thứ 2 thông qua generic để define a type cho event.

--- Multithreading trong C#

- Multithreading là 1 kỹ thuật để cùng 1 lúc có thể xử lý nhiều tác vụ. Mặc định C# có 2 luồng: main thread và luồng xử lý giao diện

--- Sự khác biệt giữa late binding và early binding trong C#

- Late binding và early binding là ví dụ về tính đa hình trong OOP

- Early binding: xảy ra tại thời điểm biên dịch. Nó kiểm tra các methods và thuộc tính của đối tượng tĩnh.

VÍ DỤ: khi gọi 1 method từ 1 object, early binding sẽ kiểm tra rằng method đó tồn tại và có thể được gọi từ đối tượng đó hay không.

- Late binding: xảy ra tại thời điểm runtime. Late binding xảy ra khi đối tượng là dynamic type - là kiểu đối tượng có type chưa được xác định cụ thể tại thời điểm biên dịch.

--- Mutex trong C#

- Trong multithreading, Mutex là 1 cơ chế đồng bộ hóa được sử dụng để đảm bảo rằng chỉ có 1 luồng ( thread ) có thể truy cập vào 1 tài nguyên cụ thể tại 1 thời điểm cụ thể. Mutex được sử dụng để tránh conflict thread và đảm bảo dữ liệu được truy cập 1 cách an toàn.

--- Overloading và Override

Cả 2 đều là những kỹ thuật giúp tạo nên tính đa hình ( Polymorphism )

Overloading - Nạp chồng: Khi các methods có cùng tên nhưng giá trị trả về lại khác nhau tại các ngữ cảnh khác nhau. Chỉ có method main() là không được nạp chồng.

Để implement overloading trong C#:

- Thay đổi số lượng tham số

- Thay đổi thứ tự tham số

- Sử dụng type khác nhau cho tham số

Override: Ghi đè lại method ở class cha mà class con kế thừa

--- Namespace trong C#

- Namespace là một keyword được dùng để khai báo ( declare ) 1 phạm vi chứa một tập hợp ( a set ) các related object.

--- Explicit Conversion trong C#

- Chuyển đổi ngầm trong C# sẽ được auto implment khi mà chúng ta convert 1 data type sang 1 data type lớn hơn.

--- Ref và Out
