-- Giải thích Promise

- Promise trong javascript là một object đặc biệt để xử lý các tác vụ bất đồng bộ, khi khởi tạo 1 promise cần truyền vào constructor của nó 1 callback với 2 tham số resolve và reject. Một Promise có 3 trạng thái: Pending, Fulfilled, Reject.
- Promise trong javascript có các methods như then() để xử lý logic ( then() sẽ nhận về 1 callback để xử lý giá trị mà promise trả khi promise được resolve ), catch để bắt lỗi, hay finally luôn được gọi cho dù promise đó được resolve hay reject
