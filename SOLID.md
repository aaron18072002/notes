- Single Responsibility Principle

--- Một class chỉ nên chịu trắc nghiệm ( be responsible for ) cho 1 công việc.

--- Một class chỉ nên có ( should have ) 1 lý do để thay đổi.

- Open-Closed Principle

- Nguyên lí Open-Closed nói rằng các Modules, Classes và Functions nên opened cho việc mở rộng ( extension ) nhưng closed cho việc modification.

- Behavior của một class hoặc module chỉ nên được thay đổi bằng cách mở rộng chức năng của nó, chứ không phải bằng cách sửa đổi logic hiện tại. Điều này có nghĩa là khi cần thêm tính năng mới hoặc thay đổi hành vi của một class, chúng ta nên thực hiện điều này bằng cách tạo ra các lớp mới hoặc các phương thức mới mà không cần phải sửa đổi trực tiếp các phần đã hoạt động.

- Interface Segregation Principle ( nguyên tắc phân chia interface )

- Một class không nên implement các methods từ 1 interface trong khi các methods không phù hợp với chính class đó.

- Dependency Inversion Principle

--- High-level module không nên depend on low-level module. Cả 2 nên depend on abstraction. Module ở đây chính là Class.
