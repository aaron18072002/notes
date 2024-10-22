- HỌC NHẤT QUÁN, HỌC LIÊN TỤC, LẤY CON A TRÍ TUỆ NHÂN TẠO ĐỂ LÊN 3.1 GPA, LẤY ĐIỂM TOEIC CAO NHẤT CÓ THỂ, CỐ GẮNG HẾT CỠ ĐỂ NĂM 2025 CÓ THỂ PASS FPT ,SAU TẾT 2025 COMBACK!

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

- METHOD OVERLOADING

-- METHOD OVERLOADING trong JAVA có nghĩa là có hai hoặc nhiều phương thức (hoặc hàm) trong một lớp có cùng tên nhưng khác nhau về đối số (hoặc tham số).
Điều này có thể thực hiện bằng cách sử dụng số lượng đối số khác nhau hoặc kiểu dữ liệu của các đối số khác nhau.

-- METHOD OVERLOADING trong JAVA không thể áp dụng chỉ dựa trên kiểu trả về (return type) của phương thức

-- METHOD main() của 1 class cũng có thể bị OVERLOADING;

- DEFINE and INVOKE METHOD

-- DEFINE và INVOKE phương thức là hai bước khác nhau. DEFINE phương thức là quá trình tạo ra một phương thức, tức là một khối mã có thể được thực thi.

-- INVOKE phương thức là quá trình kích hoạt phương thức, nghĩa là thực thi mã bên trong phương thức đó.

- PACKAGE

-- Một PACKAGE (gói) trong JAVA là một nhóm các class, interface và các package con tương tự, liên quan đến nhau.

-- PACKAGE trong JAVA được sử dụng nhằm tránh mâu thuẫn trong cách đặt tên và kiểm soát truy cập của các class, sub-class và interface. Bằng việc sử dụng các package,
lập trình viên sẽ dễ dàng sắp xếp và tìm kiếm các class, đồng thời package cung cấp một cấu trúc tốt cho dự án, đặc biệt với các dự án có lượng class và file lớn

-- Các PACKAGE được chia làm hai loại: Built-in packages và User defined packages.

- JAVA CLASS và OBJECT

-- CLASS như một TEMPLATE, có thể dung TEMPLATE này để tạo ra nhiều INSTANCES của CLASS đó.

-- Có thể xem CLASS như 1 bản thiết kế và OBJECT là các tòa nhà được xây bởi bảng thiết đó.

- OOP

-- Lập trình theo hướng OOP, chúng ta phải nghĩ về OBJECT, nghĩ về OBJECT là nghĩ về OBJECT đó có thể chứa DATA gì và nó có thể làm các chức năng gì.

-- lập trình hướng đối tượng (OOP - Object-Oriented Programming) xoay quanh việc tổ chức chương trình theo các đối tượng (OBJECTS). Mỗi đối tượng là một thực thể có
hai thành phần chính: DỮ LIỆU - hay TRẠNG THÁI của nó ( DATA - STATE ) và Chức năng (Behavior).

- MEMBER VARIABLE

-- Trong Java, MEMBER VARIABLE (biến thành viên) là các biến được khai báo trong lớp (class) nhưng nằm ngoài bất kỳ phương thức, hàm tạo (constructor), hoặc code block nào. Chúng còn được gọi là instance variables (biến thực thể) hoặc fields (trường) và là một phần quan trọng của đối tượng.

-- Mỗi OBJECT của lớp sẽ có một bản sao riêng của các biến này.

-- Các biến này có thể có giá trị khác nhau đối với mỗi OBJECT khác nhau.

-- Các MEMBER VARIABLE không nên được truy cập trực tiếp từ các OBJECTs khác mà nên được GET và SET thông qua METHOD để ngăn chặn việc các OBJECTs khác truyền vào các INVALID VALUE.
Nguyên tắc này được gọi là ENCAPSULATION (tính đóng gói).

- LOCAL VARIABLE

-- Là biến nằm trong khai báo và sử dụng trong phạm vi CODE BLOCK của 1 METHOD, 1 câu lệnh IF, 1 vòng FOR, vv...

-- Những biến này chỉ tồn tại trong phạm vi khối mã đó và sẽ không thể được truy cập từ bên ngoài.

- CONSTRUCTOR (Hàm khởi tạo)

-- CONSTRUCTOR trong java là một dạng đặc biệt của METHOD được sử dụng để khởi tạo các đối tượng.

-- Java CONSTRUCTOR được gọi tại thời điểm tạo đối tượng. Nó khởi tạo các giá trị để cung cấp dữ liệu cho các đối tượng, đó là lý do tại sao nó được gọi là CONSTRUCTOR.

- PRIMITIVE VARIABLE TYPES

-- 1 BYTE = 8 BIT.

-- BYTE: 1 BYTE, SHORT: 2 BYTEs, INT: 4 BYTEs, LONG: 8 BYTEs, FLOAT, DOUBLE: nói về số.

-- CHAR: nói về 1 ký tự.

-- BOOLEAN: giá trị là 'true' hoặc 'false'.

-- Các toán tử có thể áp dụng cho PRIMITIVE TYPEs gồm: +,-,\*,/,%,++,--.

-- LƯU Ý: Toán tử prefix increment (++) và prefix decrement (--) xảy ra trước toán tử gán (=) trong Java.

-- LƯU Ý: Không nên sử dụng FLOAT và DOUBLE và 2 TYPEs này không thể hiện chính xác các giá trị thập phân.

- CASTING

-- IMPLICIT CASTING: là quá trình Java tự động chuyển đổi từ kiểu dữ liệu thấp hơn sang kiểu dữ liệu cao hơn mà không
cần sự can thiệp của lập trình viên. Điều này thường xảy ra khi không có khả năng mất mát dữ liệu,
ví dụ từ INT sang LONG hoặc từ FLOAT sang DOUBLE.

-- EXPLICIT CASTING: xảy ra khi bạn muốn chuyển đổi từ kiểu dữ liệu cao hơn xuống kiểu thấp hơn.
Điều này yêu cầu lập trình viên phải chỉ định rõ ràng vì có khả năng mất mát dữ liệu.

- BigDecimal CLASS

-- Lớp BigDecimal Đây là một lớp mạnh mẽ được sử dụng để xử lý các số thập phân với độ chính xác cao, đặc biệt hữu ích cho
các phép toán tài chính hoặc các tính toán khoa học mà độ chính xác là rất quan trọng.

-- Lớp BigDecimal có thể xử lý các số dấu phẩy động rất lớn và rất nhỏ với độ chính xác cao nhưng bù lại một chút về độ phức tạp
thời gian.

-- BigDecimal là một IMMUTABLE CLASS trong Java, có nghĩa là giá trị của một đối tượng BigDecimal không thể bị thay đổi
sau khi nó được khởi tạo. Bất kỳ phép toán nào (như cộng, trừ, nhân, chia) trên một đối tượng BigDecimal đều tạo ra
một đối tượng BigDecimal mới với giá trị kết quả, thay vì thay đổi giá trị của đối tượng ban đầu.

-- LƯU Ý: nên dùng new BigDecimal("string"); thay vì new BigDecimal(float/double); thì giá trị sẽ chính xác hơn.
