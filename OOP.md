-- OOP

-> 4 tính chất cơ bản của OOP:

--- Tính trừu tượng ( Abstraction ): Trong C#, tính trừu tượng là tiến trình che giấu các chi tiết bên trong của một object và chỉ hiển thị chức năng chính của object đó. VD: Chúng ta biết được rằng bóp phanh là xe sẽ dừng lại cho dù không biết chi tiết là xe sẽ dừng theo cơ chế nào.

--> Trong C# có thể dùng tính trừu tượng bằng abstract và interface và 2 thứ đố khác nhau như thế nào:

- aa

--- Tính đóng gói ( Encapsulation ): Tính đóng gói thể hiện phạm vi và tính chất của một object. Trong C# thì tính đóng gói được thể hiện thông qua việc khai báo access modifier.

- private: phạm vi mặc định. các thuộc tính và phương thức của class đó chỉ được truy cập từ các object được tạo nền từ class đó

- protected: phạm vi được giới hạn bởi các object được khởi tạo từ class đó hoặc các objects được khởi tạo bởi class mà thừa kế class đó

- public: các thuộc tính và phương thức của class đó đều có thể được truy cập bởi các class khác.

- internal: Truy cập bị giới hạn trong phạm vi Assembly của dự án hiện tại, nếu trong cùng assembly của dự án thì nó giống hệt như public.

--- Tính kế thừa ( Inheritance ): Tính kế thừa là việc mà một class có thể sử dụng các thuộc tính ( properties ) và các phương thức ( methods ) của 1 class khác

--- Tính đa hình ( Polymorphism ): Tính da hình là việc cùng một thuộc tính hay phương thức nhưng giá trị trả về có thể khác nhau theo từng object tùy thuộc vào tham số truyền vào lúc khởi tạo. VD: 2 Object Honda và Mazda đều được khởi tạo từ class Car nhưng thuộc tính speed có thể khác nhau.

- Trong C# có 2 loại đa hình:

--> Đa hình tĩnh:

--> Đa hình động: Trong c# có thể dùng abstract class hoặc virutal function để triển khai đa hinh động.

---> So sánh đa hình động với abstract class và virtual function:

Giống: Đều phải khai báo virtual và abstract để có thể overide ở class thừa kế.

Khác: abstract thì bắt buộc phải overide còn virtual thì không.
