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

-- TRUNCATE và DELETE

- DELETE: Xóa một hay tất cả dòng trong một bảng theo một điều kiện nhất định, dữ liệu có thể phục hồi lại.

- TRUNCATE: Xóa toàn bộ các dòng của bảng, giải phóng bộ nhớ và không thể phục hồi lại.

- DELETE sẽ kích hoạt TRIGGER còn TRUNCATE thì ngược lại

- MỘT SỐ TÌNH HUỐNG KHÔNG THỂ XÓA DỮ LIỆU

-- Khóa ngoại (Foreign Key) cấu hình RESTRICT hoặc NO ACTION

-- Các ràng buộc duy nhất hoặc ràng buộc kiểm tra (CHECK constraint)

-- Quyền truy cập (Permissions)

-- Trong trạng thái giao dịch (Transaction)

-- Có triggers hoặc quy tắc (triggers or rules)

-- Làm thay đổi dữ liệu liên quan đến tính toán (computed data)

-- Làm thay đổi dữ liệu liên quan đến ghi lại sự kiện (auditing)

- INDEX

-- Index là một cấu trúc dữ liệu được dùng để định vị và truy cập nhanh nhất vào dữ liệu trong các bảng database.

-- Index là một cách tối ưu hiệu suất truy vấn database bằng việc giảm lượng truy cập vào bộ nhớ khi thực hiện truy vấn.

-- Nói đơn giản, index trỏ tới địa chỉ dữ liệu trong một bảng, giống như Mục lục của một cuốn sách (Gồm tên đề mục và số trang), nó giúp truy vấn trở nên nhanh chóng như việc bạn xem mục lục và tìm đúng trang cần đọc.

-- Trong cơ sở dữ liệu, chỉ mục (index) được đánh vào cột (hoặc các cột) của một bảng, chứ không phải vào dòng. Khi bạn tạo chỉ mục cho một cột, hệ thống sẽ sắp xếp dữ liệu trong cột đó và lưu trữ vị trí của các giá trị, giúp truy vấn dữ liệu từ cột đó nhanh hơn.

-- Cấu trúc của INDEX bao gồm: SEARCH KEY và DATA REFERENCE.

◇ CẨN TRỌNG KHI DÙNG INDEX:

• Index sẽ làm tốn thêm bộ nhớ để lưu trữ.
• Làm chậm các hoạt động khác, khi insert hay update column sử dụng index, index cần được điều chỉnh (reindex) sẽ tiêu tốn một khoảng thời gian.
• Việc đánh index bừa bãi, lộn xộn, không những không tăng tốc độ truy vấn mà còn làm giảm hiệu năng hoạt động.

- VIEW

-- Database View là sự trình bày data theo ý muốn được trích xuất từ một hoặc nhiều table/view khác. View không lưu data nên nó còn được biết đến với cái tên "bảng ảo(virtual tables)".

-- Các thao tác select, insert, update và delete với view tương tự như table bình thường.

-- VIEW không lưu data nên tất cả những thao tác được thực hiện trên view thì đều được phản ánh đến base table mà được trích xuất dữ liệu.

- CHECK OPTION

-- CHECK OPTION trong View là một điều kiện cho phép bạn xác định ràng buộc về việc cập nhật hoặc chèn dữ liệu vào View. Nó đảm bảo rằng các dòng dữ liệu được chèn hoặc cập nhật thông qua View sẽ tuân theo một điều kiện cụ thể.

- T-SQL

-- T-SQL (Transact-SQL) là một mở rộng của ngôn ngữ SQL tiêu chuẩn, được phát triển bởi Microsoft và Sybase để hỗ trợ các tính năng bổ sung giúp xử lý các yêu cầu phức tạp hơn trong cơ sở dữ liệu.

-- Ngoài các câu lệnh SQL tiêu chuẩn, T-SQL cung cấp các tính năng bổ sung như:

--- Kiểm soát giao dịch: Giúp đảm bảo tính toàn vẹn của dữ liệu thông qua các câu lệnh như BEGIN TRANSACTION, COMMIT, và ROLLBACK, cho phép xử lý các giao dịch (transactions) một cách an toàn.

--- Xử lý lỗi: T-SQL có các khối TRY...CATCH để xử lý lỗi, giúp bạn bắt và xử lý lỗi trong quá trình thực thi các câu lệnh SQL, tăng độ tin cậy của các thao tác cơ sở dữ liệu.

--- Khai báo và sử dụng biến: T-SQL cho phép khai báo và sử dụng biến với cú pháp DECLARE, SET, và SELECT INTO. Điều này rất hữu ích khi bạn cần lưu trữ tạm thời dữ liệu hoặc làm việc với các giá trị trong các phép tính.

--- Lập trình thủ tục: Bạn có thể viết các stored procedure (thủ tục lưu trữ), trigger, và function (hàm) với T-SQL, giúp tăng cường khả năng tái sử dụng và quản lý mã code tốt hơn.

--- Xử lý vòng lặp và rẽ nhánh: T-SQL cung cấp các cấu trúc điều khiển như IF...ELSE, WHILE, và CASE, giúp xử lý logic phức tạp trong các truy vấn và thao tác cơ sở dữ liệu.

- STORED PROCEDURE

-- STORED PROCEDURE là tập hợp một hoặc nhiều câu lệnh T-SQL thành một nhóm đơn vị xử lý logic và được lưu trữ trên Database Server.

-- Khi một câu lệnh gọi chạy STORED PROCEDURE lần đầu tiên thì SQL Server sẽ chạy nó và lưu trữ vào bộ nhớ đệm, gọi là plan cache, những lần tiếp theo SQL Server sẽ sử dụng lại plan cache nên sẽ cho tốc độ xử lý tối ưu.

-- SQL Server sẽ làm việc hiệu quả hơn nếu dùng stored procedure vì người gởi chỉ gởi một câu lệnh đơn và SQL Server chỉ kiếm tra một lần sau đó tạo ra một execute plan và thực thi. Nếu stored procedure được gọi nhiều lần thì execute plan có thể được sử dụng lại nên sẽ làm việc nhanh hơn. Ngoài ra cú pháp của các câu lệnh SQL đã được SQL Sever kiếm tra trước khi save nên nó không cần kiếm lại khi thực thi.

- TRIGGER

-- TRIGGER (kích hoạt) trong SQL là một thủ tục được lưu trữ (stored procedure) được liên kết với một TABLE hoặc VIEW.

-- TRIGGER có 2 loại: AFTER hoặc BEFORE

-- Nó sẽ tự động được thực thi khi có một sự kiện cụ thể xảy ra, chẳng hạn như INSERT, UPDATE, hoặc DELETE ( liên qua tới DDL DML ). Triggers thường được sử dụng để:

--- Kiểm tra và xác thực dữ liệu: Đảm bảo rằng dữ liệu nhập vào đáp ứng các điều kiện nhất định trước khi chấp nhận thay đổi.

--- Tự động cập nhật dữ liệu: Có thể tự động tính toán và cập nhật các cột hoặc bảng khác dựa trên các thay đổi dữ liệu.

--- Duy trì tính toàn vẹn tham chiếu: Đảm bảo rằng các ràng buộc và mối quan hệ giữa các bảng luôn được giữ vững.

--- Ghi nhật ký thay đổi: Ghi lại lịch sử thay đổi của dữ liệu cho mục đích theo dõi hoặc audit.

--- Thực thi logic nghiệp vụ phức tạp: Để phản hồi ngay lập tức với các sự kiện trong cơ sở dữ liệu mà không cần sự can thiệp từ ứng dụng.
