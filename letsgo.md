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
