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

- [_]:@ Đại diện cho 1 ký tự

- []: Đại diện cho bất kỳ ký tự nào trong ngoặc vuông.

- [^]: Đại diện cho bất kỳ ký tự nào không nằm trong ngoặc vuông.

- [char1-char2]: Đại diện cho bất kỳ ký tự nào nằm trong khoảng từ char1 đến char2.

-- IN

- Toán tử IN cho phép bạn chỉ định nhiều giá trị cho 1 field trong mệnh đề WHERE.

-- GROUP BY

- Dùng để nhóm các dòng có cùng giá trị.

- Thường dùng với các aggregate functions: COUNT(), MAX(), MIN(), SUM(), AVG().

- DISTINCT khá giống với GROUP BY và thực chất thì GROUP BY là một trường hợp đặc biệt của DISTINCT khi nó tự động sắp xếp kết quả còn DISTINCT thì không.

- GROUP BY chạy trước aggragation function.

-- HAVING

- Thay thế cho Where vì Where không thể dùng với aggregate functions. WHERE Lọc các hàng dữ liệu trước khi các phép tính toán hoặc hàm tổng hợp được thực hiện. Điều này có nghĩa là bất kỳ điều kiện nào trong câu lệnh WHERE phải dựa trên các cột hoặc giá trị của các hàng dữ liệu ban đầu.

-- UNION

- Toán tử UNION được sử dụng để kết hợp tập hợp kết quả của hai hoặc nhiều câu lệnh SELECT. Mỗi câu lệnh SELECT với UNION phải có cùng số lượng cột, các cột phải có cùng kiểu dữ liệu, các cột trong mỗi câu lệnh SELECT phải có cùng trật tự.

- UNION loại bỏ các bản ghi trùng lặp trong kết quả.

- UNION ALL giữ lại tất cả các bản ghi, bao gồm cả các bản ghi trùng lặp.

-- JOIN

- INNER JOIN: Trả về các hàng khi có ít nhất một giá trị khớp giữa các bảng. Các hàng không khớp ở cả hai bảng đều bị loại bỏ.

- LEFT OUTER JOIN (LEFT JOIN): Trả về tất cả các hàng từ bảng bên trái (Left Table), cùng với các hàng tương ứng từ bảng bên phải (Right Table). Nếu không có hàng khớp từ bảng bên phải, các cột từ bảng bên phải sẽ là NULL.

- RIGHT OUTER JOIN (RIGHT JOIN): Tương tự như LEFT JOIN, nhưng trả về tất cả các hàng từ bảng bên phải và các hàng tương ứng từ bảng bên trái. Nếu không có hàng khớp từ bảng bên trái, các cột từ bảng bên trái sẽ là NULL.

- FULL OUTER JOIN: Kết hợp giữa LEFT JOIN và RIGHT JOIN. Trả về tất cả các hàng khi có giá trị khớp trong một trong hai bảng. Nếu không có hàng khớp, các cột từ bảng thiếu sẽ là NULL.

-- SUB QUERY

- Subquery ( câu truy vấn con ) trong SQL là 1 truy vấn SELECT được viết bên trong 1 câu truy vấn SELECT, UPDATE, INSERT hoặc DELETE khác.

- Subquery hoạt động như 1 bảng ảo tạm thời, được sử dụng để lấy thông tin là các tables trong cùng 1 câu truy vấn.

- VẤN ĐỀ CỦA SUB QUERY: Khi bạn sử dụng subquery làm điều kiện trong mệnh đề WHERE, subquery sẽ được thực thi lại cho mỗi hàng trong tập dữ liệu của câu lệnh SELECT. Điều này có nghĩa là nếu truy vấn chính có 1 triệu dòng, subquery có thể sẽ được thực thi 1 triệu lần, dẫn đến hiệu suất kém và thời gian xử lý lâu hơn.

-- THỨ TỰ THỰC THI CÁC CÂU LỆNH SQL

1. FROM: SQL bắt đầu bằng cách lấy dữ liệu từ các bảng và thực hiện các phép nối (nếu có) giữa các bảng được liệt kê sau từ khóa FROM.

2. JOIN: Các phép nối (như INNER JOIN, LEFT JOIN, RIGHT JOIN,...) giữa các bảng được xử lý trong bước này. Kết quả sẽ là một bảng tạm chứa dữ liệu từ các bảng được kết nối theo điều kiện nối. JOIN diễn ra trước, xác định các bảng nào sẽ được kết nối và loại kết nối nào sẽ được thực hiện. Sau đó, điều kiện nối (câu lệnh ON) sẽ quyết định cách các bản ghi từ các bảng đó được kết hợp với nhau. Dựa trên loại JOIN, điều kiện ON sẽ xử lý khác nhau, và từ đó phân biệt giữa các kiểu INNER JOIN, LEFT JOIN, RIGHT JOIN, và FULL JOIN

3. WHERE: Sau khi có bảng tạm, các điều kiện lọc ở WHERE sẽ được áp dụng để loại bỏ các hàng không thỏa mãn điều kiện.

4. GROUP BY: Các hàng còn lại sẽ được nhóm lại dựa trên các cột chỉ định trong GROUP BY. Điều này tạo ra các nhóm dữ liệu dựa trên các giá trị chung của các cột được chỉ định.

5. HAVING: Các nhóm dữ liệu được tạo ra từ GROUP BY sẽ được lọc tiếp bởi điều kiện trong HAVING. HAVING thường được sử dụng với các hàm tổng hợp (như SUM, COUNT, AVG,...) để chỉ giữ lại các nhóm thỏa mãn điều kiện nhất định.

6. SELECT: Bước này chọn các cột và các phép tính cần lấy từ bảng tạm (hoặc nhóm dữ liệu sau khi nhóm và lọc). Các hàm tổng hợp và biểu thức sẽ được tính toán trong bước này.

7. DISTINCT: Nếu có DISTINCT, SQL sẽ loại bỏ các bản ghi trùng lặp trong kết quả đã chọn.

8. ORDER BY: Cuối cùng, SQL sắp xếp các kết quả theo cột hoặc biểu thức được chỉ định trong ORDER BY.

9. TOP / LIMIT / OFFSET: Giới hạn số lượng bản ghi trả về, thường dùng để chỉ định số lượng kết quả mong muốn hoặc phân trang.

-- COMMON TABLE EXPRESSION (CTE)

- Cho phép người dùng đặt tên và sử dụng một bảng tạm thời trong phạm vi của một truy vấn cụ thể.

- CTE được sử dụng trong việc xử lý các câu truy vấn phức tạp, thường kết hợp với các câu lệnh SELECT, INSERT, UPDATE hoặc DELETE giúp tăng tính rõ ràng, dễ đọc hiểu và quản lý các đoạn mã SQL.

-- 4 NHÓM LỆNH CHÍNH TRONG SQL

- DML (Data Manipulation Language): Các câu lệnh DML được sử dụng để thao tác với dữ liệu trong cơ sở dữ liệu, bao gồm các câu lệnh chèn, cập nhật, xóa và truy vấn.

- DDL (Data Definition Language): Các câu lệnh DDL được sử dụng để định nghĩa cấu trúc của cơ sở dữ liệu, bao gồm các bảng, cột, chỉ mục và ràng buộc.

- DCL (Data Control Language): Các câu lệnh DCL được sử dụng để kiểm soát quyền truy cập vào cơ sở dữ liệu, bao gồm các câu lệnh cấp phép và thu hồi quyền.

- TCL (Transaction Control Language): Các câu lệnh TCL được sử dụng để quản lý các giao dịch trong cơ sở dữ liệu, bao gồm các câu lệnh bắt đầu, xác nhận và hoàn tác giao dịch.

-- SELECT INTO

- Câu lệnh SELECT INTO trong SQL được sử dụng để tạo một bảng mới và sao chép dữ liệu từ một bảng hiện có vào bảng mới này.

- Nó thường được sử dụng để tạo bảng tạm thời hoặc sao lưu dữ liệu từ một bảng hiện có để thực hiện các phân tích hoặc thao tác dữ liệu khác.

- Câu lệnh SELECT INTO cũng có thể sử dụng để chọn một phần dữ liệu từ bảng nguồn và chèn nó vào bảng mới.
