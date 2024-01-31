- Props và State

* Props đơn giản chỉ là dữ liệu được truyền từ component cha xuống component con và props là giá trị bất biến ( immutable ) không thể thay đổi bởi component con và thao tác của user, chỉ có thể được thay đổi bởi component cha. Trong khi state là 1 dữ liệu động thuộc quyền sở hữu bởi chính component chứa nó và có thể được update bởi logic trong component hoặc thao tác của user với chính component đó ở phía UI.

- Vì sao lại cần props

* Props là giá trị nằm trong 1 component mà component đơn giản chỉ là 1 function. Vậy những components đó ( functions đó ) không có khả năng thay đổi các giá trị ( các props ) bên ngoài phạm vi của nó. Điều đó làm cho props trở thành 1 cơ chế one-way-data-flow từ component xuống component con. Giảm thiểu sự phức tạp trong việc xây dựng các component.

- One way binding và Two way binding trong react ( ràng buộc 1 chiều và 2 chiều )

* One way binding: Dữ liệu mà user nhìn thấy ở UI sẽ được tự động cập nhật khi source code thay đổi, không phải ngược lại.
* Two way binding: Là 1 cơ chế mà những tương tác của user làm thay đổi data thì data sẽ đó sẽ được cập nhật và source code ( ví dụ user nhập vào ô tìm kiếm ). Và ngược lại khi data thay đổi thì component sẽ re-render lại và hiển thị data mới nhất cho user.
