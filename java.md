- VÌ SAO PHẢI THIẾT LẬP PATH environment variable

-- PATH environment variable là một biến môi trường trong hệ điều hành, chứa danh sách các thư mục nơi hệ thống sẽ tìm kiếm các tệp thực thi (executables). Khi bạn nhập một
lệnh vào dòng lệnh (Command Prompt trên Windows hoặc Terminal trên macOS/Linux), hệ thống sẽ tìm kiếm các tệp thực thi trong các thư mục được liệt kê trong PATH.

-- Khi cài đặt JDK, các tệp thực thi của Java như javac và java được đặt trong thư mục bin của JDK (ví dụ: C:\Program Files\Java\jdk-21\bin trên Windows). Nếu không thêm
thư mục này vào PATH, bạn sẽ phải nhập đường dẫn đầy đủ mỗi khi muốn sử dụng các lệnh liên quan đến Java, chẳng hạn: C:\Program Files\Java\jdk-17\bin\javac MyProgram.java

- JAVA PLATFORM

-- JAVA là một ngôn ngữ độc lập với nền tảng ( PLATFORM-INDEPENDENT ) vì mã nguồn của JAVA có thể chạy trên nhiều hệ điều hành. Các chương trình Java có thể chạy trên bất kỳ máy nào hoặc hệ điều hành không cần cài đặt bất kỳ phần mềm đặc biệt nào. Mặc dù JVM cần phải có mặt trong máy để thực thi BYTECODE (.class).

-- JAVA PLATFORM bao gồm Java Virtual Machine (JVM), Java Runtime Environment (JRE), Java Development Kit (JDK), Java Application Programming Interface (API) và Java Language.

-- SOURCE CODE JAVA (.java) sau khi được COMPILE bởi trình biên dịch JAVAC sẽ trở thành BYTECODE (.class), sau đó BYTECODE sẽ được thực thi (EXECUTION) bởi JVM để trở thành ngôn ngữ máy cho từng loại HỆ ĐIỀU HÀNH.

- JDK

-- JDK (Java Development Kit) là bộ công cụ phần mềm cần thiết cho việc phát triển ứng dụng Java. JRM + COMPLILERS + DEBUGGER.

-- Java Runtime Environment (JRE): Môi trường chạy cho ứng dụng Java, chứa JVM (Java Virtual Machine) và các thư viện liên quan tới JAVA.

-- JVM(Java Virtual Machine): thực thi BYTECODE (.class). Tuy nhiên, mỗi hệ điều hành (Windows, macOS, Linux, v.v.) sẽ có JVM riêng để thực thi BYTECODE theo cách phù hợp
với hệ điều hành đó.

-- Trình biên dịch - DEBUGGER Java (javac): Công cụ để biên dịch mã nguồn Java (.java) thành mã BYTECODE (.class) mà JVM có thể hiểu và thực thi.

- JSHELL

-- JSHELL được phát hành từ JAVA 9.

-- JSHELL là công cụ REPL đầu tiên được tích hợp trong Java.

-- Nó cho phép các lập trình viên chạy các lệnh và biểu thức Java tương tác trực tiếp trong console mà không cần phải bọc chúng trong các lớp hoặc phương thức.

- JAVA CLASS và OBJECT

-- CLASS như một TEMPLATE, có thể dung TEMPLATE này để tạo ra nhiều INSTANCES của CLASS đó.

-- Có thể xem CLASS như 1 bản thiết kế và OBJECT là các tòa nhà được xây bởi bảng thiết đó.

- JAVA EXPRESSION - BIỂU THỨC

-- EXPRESSION là sự kết hợp giữa các giá trị, biến, toán tử, và các lời gọi phương thức, được tính toán để cho ra một giá trị duy nhất.
Biểu thức có thể là một giá trị đơn lẻ hoặc một tổ hợp các giá trị mà khi được đánh giá sẽ tạo ra kết quả. Biểu thức có thể được sử dụng trong nhiều ngữ cảnh,
chẳng hạn như trong phép gán giá trị, các câu lệnh điều kiện, và các vòng lặp.

- PRINT, PRINTLN và PRINTF

-- Với PRINT: Xuất kết quả ra màn hình nhưng con trỏ chuột không xuống dòng.

-- Với PRINTLN: Xuất kết quả ra màn hình đồng thời con trỏ chuột nhảy xuống dòng tiếp theo.

-- Với PRINTF: Xuất ra màng hình kết quả đồng thời có thể định dạng được kết quả đó nhờ vào các ARGUMENTS và FORMAT SPECIFER (định dạng chuỗi) thích hợp.

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
