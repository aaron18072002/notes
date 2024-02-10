-- Props và State

- Props đơn giản chỉ là dữ liệu được truyền từ component cha xuống component con và props là giá trị bất biến ( immutable ) không thể thay đổi bởi component con và thao tác của user, chỉ có thể được thay đổi bởi component cha. Trong khi state là 1 dữ liệu động thuộc quyền sở hữu bởi chính component chứa nó và có thể được update bởi logic trong component hoặc thao tác của user với chính component đó ở phía UI.

-- Vì sao lại cần props

- Props là giá trị nằm trong 1 component mà component đơn giản chỉ là 1 function. Vậy những components đó ( functions đó ) không có khả năng thay đổi các giá trị ( các props ) bên ngoài phạm vi của nó. Điều đó làm cho props trở thành 1 cơ chế one-way-data-flow từ component xuống component con. Giảm thiểu sự phức tạp trong việc xây dựng các component.

-- Children - 1 kiểu props đặc biệt

- Trong React, mỗi component có một prop gọi là Children, cho phép bạn truyền các DOM element bên trong component từ component cha xuống component con. Children không cần phải được khai báo trong danh sách các prop khi định nghĩa component, mà React tự động đưa nó vào trong props của mỗi component.

-- One way binding và Two way binding trong react ( ràng buộc 1 chiều và 2 chiều )

- One way binding: Dữ liệu mà user nhìn thấy ở UI sẽ được tự động cập nhật khi source code thay đổi, không phải ngược lại.
- Two way binding: Là 1 cơ chế mà những tương tác của user làm thay đổi data thì data sẽ đó sẽ được cập nhật và source code ( ví dụ user nhập vào ô tìm kiếm ). Và ngược lại khi data thay đổi thì component sẽ re-render lại và hiển thị data mới nhất cho user.

-- Component là gì?

- Components trong reactjs là các hàm hoặc class đại diện cho từng thành phần trong UI.

-- Các tính chất mà Component cần có?

- Reusability ( Tính tái sử dụng vì một component có thể được gọi ở nhiều nơi trong app của chúng ta ).
- Maintainability ( Tính dễ bảo trì vì một component quá phức tạp khi gặp bug sẽ rất khó để sửa lỗi ).
- Effectively: Mỗi component đều phải đảm nhận một vai trò hợp lí ( không đảm nhận quá nhiều layout và logic vì sẽ khiến component quá phức tạp để có thể tái sử dụng và bảo trì ).

-- Các loại components ?

- Stateless component.
- Stateful component.
- Structural component là loại component mà nó sẽ có cấu trúc phức tạp hơn 1 component thông thường ( Layouts, Pages, ... ). Structural Component là kết quả của components composition.

-- JSX ( Javascript eXtensible Markup Languege )

- Theo như react.dev, JSX là một cú pháp mở rộng cho Javascript cho phép viết HTML-like markup bên trong Javascript file.
- JSX hoạt động về cơ bản giống HTML, nhưng chúng ta có thể viết JS với nó nếu dùng dấu ngoặc nhọn ( curly braces {} )
- Chúng ta chỉ có thể đặt một Javascript Expesstions vào trong {} ( ví dụ như toán tử 3 ngôi sẽ trả về 1 js expression, hay [].map sẽ trả về 1 array mới,... ).
- Statements ( các câu lệnh ) sẽ không truyền vào được {} ( ví dụ như if/else hay swich case,... ).
- JSX tạo ra 1 JS Expression bởi vì các cú pháp JSX sẽ được convert thành các lời gọi hàm React.createElement().
