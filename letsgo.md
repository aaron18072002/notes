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

--- Collection trong C#

- Những class mà dùng để chứa ( storage ) và truy xuất ( retrieval ) dữ liệu được gọi là các collection classes. Những class này hỗ trợ các cấu trúc dữ liệu như stacks, queues, lists, hash tables.

- Những collection classes có vai trò như cấp phát động ( dynamic allocating ) bộ nhớ cho các element hoặc truy cập vào list các item bằng index hoặc key ( trong khi array chỉ có thể truy cập vào element bằng index ).

- 1 số các collection classes

--> ArrayList: Giống như array nhưng mà nó có thể thay đổi độ dài, thêm, xóa phần tử 1 cách linh hoạt.

--> HashTable: Các element được lưu trữ dưới dạng key-value và có thể được truy xuất bởi key

--> StoredList:

--> Stack:

--> Queue:

--> BitArray:
