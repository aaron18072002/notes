-- ACID

-- SELECT DISTINCT

- Lấy giá trị không trùng lặp của các cột (fields) trong table

- VD: SELECT Field1, Field2 FROM Table1 - Ý nghĩa là query data từ field1, field2 của table1 với các records là không được giống nhau. Nói cách khác nếu ta query 1 fields có nhiều record có value giống nhau thì không trả về toàn bộ records đó mà chỉ trả về 1 record chứa value chung.

-- COUNT, SUM, AVG - Aggregate Query

- Hàm COUNT() chỉ đếm số lượng data khác NULL trong 1 column.

- Nếu có bất kỳ giá trị nào trong column = NULL, SUM sẽ trả về NULL.

- Nếu tất cả các giá trị trong column trả về NULL, hàm AVG sẽ trả về NULL. Còn nếu chỉ 1 vài giá trị là NULL, hàm AVG sẽ bỏ qua các giá trị NULL và tính trung bình cho các giá trị còn lại.
