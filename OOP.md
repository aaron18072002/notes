-- OOP

-> 4 tính chất cơ bản của OOP:

--- Tính trừu tượng ( Abstraction ): Trong C#, tính trừu tượng là tiến trình che giấu các chi tiết bên trong của một object và chỉ hiển thị chức năng chính của object đó. VD: Chúng ta biết được rằng bóp phanh là xe sẽ dừng lại cho dù không biết chi tiết là xe sẽ dừng theo cơ chế nào.

--> Trong C# có thể dùng tính trừu tượng bằng abstract và interface và 2 thứ đó khác nhau như thế nào:

- Interface cũng giống như abstract class, không dùng để tạo ra các object mà dùng để tạo ra các cơ sở cho các lớp kế thửa. Những khác với Abstract class, các phương thức của interface mặc định là abstract methods, vì vậy các lớp thừa kế bắt buộc phải override lại các phương thức đó ( không cần từ khóa override ). Một lớp kế thừa có thể kế thừa nhiều interface và có nghiệm vụ bắt buộc phải ghi đè lại các phương thức trong interface đó.

--- Tính đóng gói ( Encapsulation ): Tính đóng gói thể hiện phạm vi và tính chất của một object. Trong C# thì tính đóng gói được thể hiện thông qua việc khai báo access modifier.

- private - phạm vi mặc định: Các methods cùng cấp trong cùng class cũng không thể gọi các private properties và private methods. Không thể truy cập được từ bên ngoài class cũng như không thể truy cập bởi các class kế thừa.

- protected: Không thể truy cập được từ bên ngoài class nhưng các class thừa kế có thể truy cập được.

- public: các thuộc tính và phương thức của class đó đều có thể được truy cập từ bên ngoài class đó bởi mọi class khác.

- internal: Truy cập bị giới hạn trong phạm vi Assembly của dự án hiện tại, nếu trong cùng assembly của dự án thì nó giống hệt như public.

- protected internal: các thuộc tính và methods của protected interal class có thể được truy cập bởi class trong cùng 1 Assembly từ các class con thừa hưởng class đó.

--- Tính kế thừa ( Inheritance ): Tính kế thừa là việc mà một class có thể sử dụng các thuộc tính ( properties ) và các phương thức ( methods ) của 1 class khác. Một biến của class cha có thể được gán lại bởi class con nhưng ngược lại thì không.

--- Tính đa hình ( Polymorphism ): Tính da hình là việc cùng một thuộc tính hay phương thức nhưng giá trị trả về có thể khác nhau theo từng object tùy thuộc vào tham số truyền vào lúc khởi tạo. VD: 2 Object Honda và Mazda đều được khởi tạo từ class Car nhưng thuộc tính speed có thể khác nhau.

- Trong C# có 2 loại đa hình:

---> Đa hình tĩnh thể hiện qua overload method, còn đa hình động chính là override lại phương thức đó khi kế thừa.

---> So sánh đa hình động với abstract class và virtual methods ( 1 phương thức ảo là 1 phương thức có thể ghi đề được ):

Giống: Đều phải khai báo virtual và abstract để có thể overide ở class thừa kế.

Khác: Các Class con kế thừa abstract class phải override abstract method ở lớp cha. Còn với virtual methods thì nếu các methods ở lớp cha phù hợp với lớp con rồi thì không cần phải override.

-- Virtual Method

- Là các method được định nghĩa trong lớp cơ sở, có thể được ghi đè ở lớp thừa kế.

-- Dependency Inversion Principle

--- Là nguyên lí cuối cùng trong SOLID, trong đó:

- Các module cấp cao không phụ thuộc vào các module cấp thấp. Cả 2 nên phụ thuộc vào abstraction.

- Các Class giao tiếp thông qua interface, không phải việc implement.

- VD: Với code thông thường, các module cấp cao sẽ phụ thuộc vào các module cấp thấp, tạo ra các dependency. Trong trường hợp đó, khi các module cấp thấp thay đổi thì các module cấp cao phải thay đổi theo. Dẫn đến việc code thay đổi nhiều, khó maintain.

-- Inversion of control

--- Là 1 design pattern được tạo ra để code có thể tuân theo nguyên lý Dependency Inversion. Có nhiều cách để thực hiện pattern này, Dependency Injection là 1 trong số đó.

-- Dependency Injection

--- Là 1 kỹ thuật sử dụng da hình động ( dynamic pholymorphism ) để thực hiện hóa Inversion Of Control Pattern, nhắm giúp code của chúng ta tuân thủ theo nguyên lý Dependency Inversion.

--- DI được dùng để giảm sự phụ thuộc giữa các object, giúp chúng ta dễ dàng thay đổi code hơn, dễ maintain hơn.

--- Các module phụ thuộc ( dependency ) sẽ được inject vào các module cấp cao:

- Các module không implement trực tiếp với nhau, mà thông qua interface. Các module cấp thấp sẽ implment interface, sau đó các module cấp cao sẽ implment các module cấp thấp thông qua interface.

- Việc khởi tạo các module cấp thấp sẽ được DI Container thực hiện.

--- Có 3 loại Dependency Injection:

- Constructor injection:

- Setter injection:

- Interface injection:

-- Proxy và Reverse Proxy, Load Balance

- Proxy là một server trung gian nằm giữa client và server. Nhận request từ client rồi chuyển tiếp nó đến server hoặc ngược lại. Proxy đóng vai trò như một tường lửa để bảo vệ client, cung cấp một số tính năng như caching, ẩn địa chỉ IP của client.

- Reverse Proxy là một loại Proxy đặc biệt nằm trước server Back End, có nghiệm vụ bảo vệ server, có nghiệm vụ điều hướng các request tới từng server. Reverse Proxy có thể đóng vai trò như 1 Load Balancer.

- Load Balancer là một chức năng của Reverse Proxy, có nghiệm vụ phân phối các client requests hoặc network load một cách hiệu quả trên nhiều servers.
