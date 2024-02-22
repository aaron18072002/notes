-- Design pattern

-> Design pattern là khái niệm để nói về các mô hình, kiến trúc, các kiểu thiết kế phần mềm hoặc hệ thống.

-> Có 3 loại design pattern phổ biến
--- Creational: Bao gồm những loại patterns cung cấp solutions để tạo ra các object 1 cách linh hoạt.
---- Singleton
---- Factory Method: Factory method cung cấp 1 interface cho việc tạo ra các object nhưng nó cho phép các subclasses ( lớp con ) là những class mà implement cái interface đó thay đổi kiểu object mà nó tạo ra theo các business logic cụ thể.
VD: Giả sử chúng ta có 1 ứng dụng quản lý giao thông. Nhưng ứng dụng đó chỉ có thể tạo ra các object từ class Car dẫn đến việc ứng dụng của chúng ta chỉ có thể handle các request từ đường bộ. Nhưng sau đó khách hàng muốn ứng dụng chúng ta handle thêm các request từ đường biển. Nếu như dùng if else mỗi lần tạo ra các object mới thì sẽ bị tình trạng lặp code và không linh hoạt.
---- Abstract Factory
---- Builder
---- Prototype
