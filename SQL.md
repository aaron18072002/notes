-- ACID

-- SELECT DISTINCT

- Lấy giá trị không trùng lặp của các cột (fields) trong table

- VD: SELECT Field1, Field2 FROM Table1 - Ý nghĩa là query data từ field1, field2 của table1 với các records là không được giống nhau. Nói cách khác nếu ta query 1 fields có nhiều record có value giống nhau thì không trả về toàn bộ records đó mà chỉ trả về 1 record chứa value chung.

-- COUNT, SUM, AVG - Aggregate Query

- Hàm COUNT() chỉ đếm số lượng data khác NULL trong 1 column.

- Nếu có bất kỳ giá trị nào trong column = NULL, SUM sẽ trả về NULL.

- Nếu tất cả các giá trị trong column trả về NULL, hàm AVG sẽ trả về NULL. Còn nếu chỉ 1 vài giá trị là NULL, hàm AVG sẽ bỏ qua các giá trị NULL và tính trung bình cho các giá trị còn lại.

-- Toán tử LOGIC

- AND (trả về true nếu cả hai điều kiện đều đúng)

- OR (trả về true nếu một trong hai điều kiện đúng)

- NOT (trả về true nếu điều kiện sai)

-- Toán tử đặc biệt

- BETWEEN (trả về true nếu giá trị nằm trong phạm vi được chỉ định).

- IN (trả về true nếu giá trị nằm trong danh sách được chỉ định).

- LIKE (trả về true nếu giá trị khớp với mẫu đã chỉ định) - thường dùng để lọc dữ liệu trong chuỗi: % - đại diện cho không hoặc nhiều ký tự, \_ - đại diện cho 1 ký tự.

- IS NULL (trả về true nếu giá trị null).

- EXISTS (trả về true nếu truy vấn con trả về bất kỳ hàng nào).

-- WILDCARD

- %: Đại diện cho 1 hoặc không có ký tự nào hoặc nhiều ký tự.

- []: Đại diện cho bất kỳ ký tự nào trong ngoặc vuông.

- [^]: Đại diện cho bất kỳ ký tự nào không nằm trong ngoặc vuông.

- [char1-char2]: Đại diện cho bất kỳ ký tự nào nằm trong khoảng từ char1 đến char2.

-- IN

- Toán tử IN cho phép bạn chỉ định nhiều giá trị cho 1 field trong mệnh đề WHERE.

-- GROUP BY

- Dùng để nhóm các dòng có cùng giá trị.

- Thường dùng với các hàm: COUNT(), MAX(), MIN(), SUM(), AVG().

- DISTINCT khá giống với GROUP BY và thực chất thì GROUP BY là một trường hợp đặc biệt của DISTINCT khi nó tự động sắp xếp kết quả còn DISTINCT thì không.
