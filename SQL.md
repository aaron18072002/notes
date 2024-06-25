-- SELECT DISTINCT

- Lấy giá trị không trùng lặp của các cột (fields) trong table

- VD: SELECT Field1, Field2  FROM Table1 - Ý nghĩa là query data từ field1, field2 của table1 với các records là không được giống nhau. Nói cách khác nếu ta query 1 fields có nhiều record có value giống nhau thì không trả về toàn bộ records đó mà chỉ trả về 1 record chứa value chung.