- JAVA PLATFORM

-- CODE JAVA sau khi được COMPILE sẽ trở thành BYTECODE, sau đó BYCODE sẽ được thực thi (EXECUTION) bởi JVM đề trở thành ngôn ngữ máy cho từng loại
HỆ ĐIỀU HÀNH.

- JDK

-- JDK (Java Development Kit) là bộ công cụ phần mềm cần thiết cho việc phát triển ứng dụng Java. Nó bao gồm:

--- Java Runtime Environment (JRE): Môi trường chạy cho ứng dụng Java, chứa JVM (Java Virtual Machine) và các thư viện cơ bản.

---- JVM(Java Virtual Machine):

--- Trình biên dịch Java (javac): Công cụ để biên dịch mã nguồn Java (.java) thành mã bytecode (.class) mà JVM có thể hiểu và thực thi.

--- Các công cụ phát triển: Bao gồm trình gỡ lỗi, trình tối ưu hóa, và nhiều công cụ khác để hỗ trợ lập trình viên trong việc viết và kiểm tra mã nguồn.

- JSHELL

-- JSHELL được phát hành từ JAVA 9.

-- JSHELL là công cụ REPL đầu tiên được tích hợp trong Java.

-- Nó cho phép các lập trình viên chạy các lệnh và biểu thức Java tương tác trực tiếp trong console mà không cần phải bọc chúng trong các lớp hoặc phương thức.

- JAVA EXPRESSION - BIỂU THỨC

-- EXPRESSION là sự kết hợp giữa các giá trị, biến, toán tử, và các lời gọi phương thức, được tính toán để cho ra một giá trị duy nhất.
Biểu thức có thể là một giá trị đơn lẻ hoặc một tổ hợp các giá trị mà khi được đánh giá sẽ tạo ra kết quả. Biểu thức có thể được sử dụng trong nhiều ngữ cảnh,
chẳng hạn như trong phép gán giá trị, các câu lệnh điều kiện, và các vòng lặp.

- PRINT, PRINTLN và PRINTF

-- Với PRINT: Xuất kết quả ra màn hình nhưng con trỏ chuột không xuống dòng.

-- Với PRINTLN: Xuất kết quả ra màn hình đồng thời con trỏ chuột nhảy xuống dòng tiếp theo.

-- Với PRINTF: Xuất ra màng hình kết quả đồng thời có thể định dạng được kết quả đó nhờ vào các ARGUMENTS thích hợp.

- ESCAPE SEQUENCE

-- Trong Java, các chuỗi thoát (ESCAPE SEQUENCE) là các ký tự đặc biệt được sử dụng trong chuỗi để biểu diễn các ký tự điều khiển, ký tự không in ra được,
hoặc khoảng trắng cụ thể. Mỗi chuỗi thoát bắt đầu bằng dấu gạch chéo ngược (\), theo sau là một ký tự đại diện cho hiệu ứng mong muốn.
Dưới đây là các chuỗi thoát phổ biến trong Java: \t, \n, ...

- VARIABLE ( BIẾN )

-- Khái niệm biến (VARIABLE) trong lập trình được sinh ra để chúng ta không cần phải cố định (hard-code) dữ liệu trong mã nguồn.
Biến cho phép bạn lưu trữ giá trị hoặc thông tin để có thể thay đổi trong quá trình chương trình chạy.

-- VARIABLE là 1 thứ mà giá trị của nó có thể thay đổi trong suốt vòng đời của ứng dụng.

-- Trong JAVA, biến được sử dụng để lưu trữ và thao tác với dữ liệu. Nó là một NAMED MEMORY LOCATION, có thể chứa một giá trị thuộc một kiểu dữ liệu cụ thể.
Từ khóa "VARIABLE" được sử dụng để khai báo và định nghĩa các biến, cho phép phân bổ bộ nhớ để lưu trữ dữ liệu trong quá trình thực thi chương trình.

- PRIMITIVE VARIABLE TYPES

-- BYTE, SHORT, INT, LONG, FLOAT, DOUBLE: nói về số.

-- CHAR: nói về 1 ký tự.

-- BOOLEAN: giá trị là 'true' hoặc 'false'.

- METHOD OVERLOADING

-- METHOD OVERLOADING trong JAVA có nghĩa là có hai hoặc nhiều phương thức (hoặc hàm) trong một lớp có cùng tên nhưng khác nhau về đối số (hoặc tham số). Điều này có thể thực hiện bằng cách sử dụng số lượng đối số khác nhau hoặc kiểu dữ liệu của các đối số khác nhau.

-- METHOD OVERLOADING trong JAVA không thể áp dụng chỉ dựa trên kiểu trả về (return type) của phương thức

-- METHOD main() của 1 class cũng có thể bị OVERLOADING;

- DEFINE and INVOKE METHOD

-- DEFINE và INVOKE phương thức là hai bước khác nhau. DEFINE phương thức là quá trình tạo ra một phương thức, tức là một khối mã có thể được thực thi.

-- INVOKE phương thức là quá trình kích hoạt phương thức, nghĩa là thực thi mã bên trong phương thức đó.
