- HỌC NHẤT QUÁN, HỌC LIÊN TỤC, LẤY CON A TRÍ TUỆ NHÂN TẠO ĐỂ LÊN 3.1 GPA, LẤY ĐIỂM TOEIC CAO NHẤT CÓ THỂ, CỐ GẮNG HẾT CỠ ĐỂ NĂM 2025 CÓ THỂ PASS FPT ,SAU TẾT 2025 COMBACK!

- VÌ SAO PHẢI THIẾT LẬP PATH environment variable

-- PATH environment variable là một biến môi trường trong hệ điều hành, chứa danh sách các thư mục nơi hệ thống sẽ tìm kiếm các tệp thực thi (executables). Khi bạn nhập một
lệnh vào dòng lệnh (Command Prompt trên Windows hoặc Terminal trên macOS/Linux), hệ thống sẽ tìm kiếm các tệp thực thi trong các thư mục được liệt kê trong PATH.

-- Khi cài đặt JDK, các tệp thực thi của Java như javac và java được đặt trong thư mục bin của JDK (ví dụ: C:\Program Files\Java\jdk-21\bin trên Windows). Nếu không thêm
thư mục này vào PATH, bạn sẽ phải nhập đường dẫn đầy đủ mỗi khi muốn sử dụng các lệnh liên quan đến Java, chẳng hạn: C:\Program Files\Java\jdk-17\bin\javac MyProgram.java

- JAVA PLATFORM

-- JAVA là một ngôn ngữ độc lập với nền tảng ( PLATFORM-INDEPENDENT ) vì mã nguồn của JAVA có thể chạy trên nhiều hệ điều hành. Các chương trình Java có thể chạy trên bất kỳ
máy nào hoặc hệ điều hành không cần cài đặt bất kỳ phần mềm đặc biệt nào. Mặc dù JVM cần phải có mặt trong máy để thực thi BYTECODE (.class).

-- JAVA PLATFORM bao gồm Java Virtual Machine (JVM), Java Runtime Environment (JRE), Java Development Kit (JDK), Java Application Programming Interface (API) và Java Language.

-- SOURCE CODE JAVA (.java) sau khi được COMPILE bởi trình biên dịch JAVAC sẽ trở thành BYTECODE (.class), sau đó BYTECODE sẽ được thực thi (EXECUTION) bởi JVM để trở thành
ngôn ngữ máy cho từng loại HỆ ĐIỀU HÀNH.

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

-- CHAR - 2 BYTEs: sử dụng 2 byte (16 bit) để biểu diễn một ký tự, và nó dựa trên tiêu chuẩn Unicode.

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

- TOÁN TỬ && và &

-- && là toán tử AND logic ngắn mạch (short-circuit). Điều này có nghĩa là nếu biểu thức bên trái là false,
thì biểu thức bên phải sẽ không được đánh giá vì toàn bộ biểu thức đã biết là false.

-- Toán tử & sẽ tiếp tục tính toán biểu thức bên phải ngay cả khi biểu thức bên trái đã false.

- DEFAULT, BREAK và FALL-THROUGH trong SWITCH CASE

-- DEFAULT là một phần của cấu trúc switch-case, được sử dụng khi không có trường hợp nào (case) khớp với giá trị cần so sánh.
Nó tương tự như else trong một câu lệnh if-else. DEFAULT không bắt buộc phải có trong switch-case, nhưng nếu có, nó thường là câu lệnh cuối cùng.

-- BREAK trong switch-case dùng để kết thúc một case. Nó giúp ngăn chặn việc thực hiện tiếp các case khác sau khi một case đã khớp.
Nếu không có BREAK, sau khi một case khớp, chương trình sẽ tiếp tục thực hiện các câu lệnh trong các case phía dưới (đây gọi là fall-through).

-- Chỉ có SWITCH có các TYPEs như INT, CHAR, STRING (JAVA 7) ,BYTE, SHORT hoặc ENUM (JAVA 5).

- TERNARY OPERATION (TOÁN TỬ 3 NGÔI)

-- Cả 2 vế của TOÁN TỬ 3 NGÔI phải trả về cùng 1 kiểu dữ liệu.

- WHILE, DO WHILE và FOR

-- Dùng FOR khi ta xác định số lần chạy.

-- WHILE sẽ kiểm tra CONDITION trước khi chạy còn DO WHILE sẽ chạy code trong block rồi mới check CONDITION.

-- Dùng DO WHILE khi muốn code trong block được EXCECUTE ít nhất 1 lần.

- BREAK và CONTINUE

-- BREAK sẽ ngay lập tức thoát khỏi tất cả lần lặp còn lại.

-- CONTINUE sẽ ngay lập tức thoát khỏi lần lặp hiện tại.

- REFERENCE TYPEs

-- Khi khai báo một biến kiểu REFERENCE TYPEs (ví dụ như một đối tượng của một class), biến này sẽ nằm trong STACK.
Biến của REFERENCE TYPEs sẽ chỉ chứa địa chỉ của đối tượng dữ liệu tại bộ nhớ STACK.
Đối tượng thực sự được tạo trong vùng nhớ HEAP. Biến tham chiếu trên STACK sẽ chứa địa chỉ trỏ đến vị trí của đối tượng này trên HEAP.

- STACK và HEAP

-- Nếu khai báo trong phương thức, hàm, hoặc khối mã, biến PRIMITIVE sẽ được lưu trong STACK vì nó có phạm vi giới hạn
và được quản lý bởi ngăn xếp trong quá trình thực thi.

-- Nếu là MEMBER VARIABLE của một đối tượng, dù có là PRIMITIVE hay không, nó sẽ được lưu trong HEAP, cùng với đối tượng mà nó thuộc về.

- STRING trong JAVA

-- STRING là 1 CLASS đặc biệt trong JAVA, khác với các class khác, ta không cần gọi CONSTRUCTOR khi khai báo 1 INSTANCE của class STRING.

-- Mọi chuỗi-string đều là INSTANCE của lớp có kiểu là STRING.

-- STRING là 1 IMMUTABLE, có nghĩa là khi một đối tượng của lớp String được tạo ra, giá trị của nó không thể thay đổi được.
Bất kỳ thao tác nào thay đổi giá trị của String sẽ tạo ra một đối tượng String mới thay vì thay đổi nội dung của đối tượng ban đầu.

-- Trong Java, chuỗi (String) thực chất là một mảng các ký tự (char) được sắp xếp liền kề trong bộ nhớ.

- String, StringBuffer và StringBuilder trong JAVA

-- Khu vực lưu trữ: Với String, String Pool đóng vai trò là khu vực lưu trữ. Đối với StringBuilder và StringBuffer, bộ nhớ HEAP là vùng lưu trữ.

-- Tính thay đổi: Một String là IMMUTABLE, trong khi cả StringBuilder và StringBuffer đều có thể thay đổi.

-- Thread-safe: Trong trường hợp môi trường luồng, StringBuilder và StringBuffer được sử dụng trong khi một String không được sử dụng.
Tuy nhiên, StringBuilder phù hợp với môi trường có một luồng duy nhất và StringBuffer phù hợp với đa luồng.

- WRAPPER CLASS

-- Trong Java, các Wrapper Class được thiết kế để "bọc" (wrap) các kiểu dữ liệu nguyên thủy (như int, double, boolean, v.v.) thành các đối tượng, từ đó cho phép xử lý
các giá trị nguyên thủy như thể chúng là các đối tượng. Điều này rất hữu ích vì:

++ Chuyển đổi giữa kiểu nguyên thủy và đối tượng: Các wrapper class cung cấp các phương thức để chuyển đổi qua lại giữa kiểu nguyên thủy và đối tượng.
Ví dụ: Integer có phương thức parseInt() để chuyển đổi String thành int.

- AUTO BOXING

-- Autoboxing hay Boxing trong JAVA là quá trình chuyển dữ liệu từ kiểu tham trị sang kiểu tham chiếu.
Khi bạn gán một giá trị nguyên thủy vào một biến tham chiếu của lớp bao, Java sẽ tự động tạo một đối tượng
(instance) của lớp bao này trên vùng nhớ HEAP và gán giá trị của kiểu nguyên thủy vào đó.

++ Hỗ trợ Collection Framework:

-- Trong Java, có hai cách phổ biến để tạo một đối tượng của Wrapper Class: phương thức valueOf() và từ khóa NEW.

-- Khi sử dụng phương thức valueOf() trong các wrapper class như Integer, Double, Boolean, v.v., Java sẽ cố gắng tái sử dụng (reuse) các đối tượng
có giá trị đã được tạo trước đó, thay vì tạo đối tượng mới mỗi lần. Cơ chế này được gọi là caching và giúp tiết kiệm bộ nhớ, đặc biệt là với các giá trị thường xuyên được sử dụng.

- DATETIME API trong JAVA

-- JAVA 8 đã giới thiệu ba lớp quan trọng trong gói java.time để làm việc với ngày và giờ là LocalDate, LocalDateTime và LocalTime.

-- Cả ba lớp LocalDate, LocalTime, và LocalDateTime trong Java 8 đều là immutable. Điều này có nghĩa là một khi đã khởi tạo,
các đối tượng từ những lớp này không thể thay đổi được. Mọi thao tác trên những đối tượng này, chẳng hạn như cộng thêm hoặc
trừ bớt ngày, giờ, sẽ tạo ra một đối tượng mới thay vì thay đổi đối tượng ban đầu.

- ARRAY

-- Array không phải là 1 COLLECTION.

-- ARRAY là cấu trúc cơ bản trong Java cho phép chúng ta lưu trữ nhiều giá trị có cùng kiểu giá trị trong một biến duy nhất.

-- Trong JAVA, các phần tử trong một mảng (ARRAY) đều được lưu trữ ở các vị trí bộ nhớ liên tiếp nhau.

-- Kích thước cố định: Khi đã tạo, Array có kích thước cố định và không thể thay đổi. Bạn phải biết số phần tử cần lưu trữ ngay từ đầu.
Nghĩa là không thể thêm và xóa phần tử của 1 ARRAY đã được khởi tạo.

- ARRAYLIST

-- Trong Java, ArrayList là 1 COLLECTION. Do đó, nó chỉ có thể chứa các kiểu tham chiếu (reference types),
không thể chứa trực tiếp các kiểu nguyên thủy (primitive types) như int, double, boolean, v.v.

- VARIABLE ARGUMENT - Varargs

-- https://viblo.asia/p/java-core-tat-tan-tat-ve-varargs-trong-java-WAyK8reelxX#_1-dat-van-de-0

- FINAL

-- Sử dụng với biến: Khi một biến được khai báo với từ khóa final, giá trị của nó không thể thay đổi sau khi được khởi tạo. Điều này tương tự như một hằng số. Khác với CONST Biến FINAL có thể được khởi tạo ở giai đoạn runtime bằng CONSTRUCTOR.

-- Sử dụng với phương thức: Khi một phương thức được khai báo là final, phương thức này không thể bị ghi đè (override) bởi các lớp con.

-- Sử dụng với lớp: Khi một lớp được khai báo là final, lớp đó không thể được kế thừa.

- DEFAULT

-- Kể từ Java 8, có thể định nghĩa các phương thức có thân (body) trong một interface bằng cách sử dụng từ khóa default. Điều này cho phép các interface cung cấp các phương thức mặc định mà các lớp triển khai có thể sử dụng hoặc ghi đè.

- INHERITANCE

-- Kế thừa là sự liên quan giữa hai class với nhau, trong đó có class cha (superclass) và class con (subclass).
Khi kế thừa class con được hưởng tất cả các phương thức và thuộc tính của class cha. Tuy nhiên, nó chỉ được truy cập các thành viên public và protected của class cha.
Nó không được phép truy cập đến thành viên private của class cha.

-- Trong Java, khi một đối tượng con được tạo, một đối tượng cha cũng được khởi tạo ngầm. Điều này xảy ra vì lớp con luôn phải gọi constructor của lớp cha,
trực tiếp hoặc gián tiếp. Nếu bạn không gọi constructor của lớp cha rõ ràng bằng từ khóa super(), Java sẽ tự động gọi constructor
không tham số (nếu có) của lớp cha trước khi thực hiện constructor của lớp con. Quy trình này giúp đảm bảo rằng tất cả các phần thuộc lớp cha đều
được khởi tạo trước khi lớp con có thể sử dụng.

-- Trong Java, nếu một lớp không mở rộng (extend) bất kỳ lớp nào, thì nó mặc định sẽ kế thừa lớp Object. Object là lớp gốc của tất cả các lớp
trong Java và cung cấp một số phương thức cơ bản như toString(), equals(), hashCode(), và clone(). Do đó, ngay cả khi bạn không viết
extends Object, mọi lớp trong Java vẫn kế thừa lớp Object và có thể sử dụng các phương thức này.

-- JAVA không hỗ trợ đa kế thừa (multiple inheritance) để tránh vấn đề "diamond problem". Vấn đề này xảy ra khi một lớp kế thừa từ hai lớp cha,
mà cả hai lớp cha này đều có phương thức cùng tên và cùng tham số (signature). Khi đó, trình biên dịch sẽ gặp khó khăn trong việc xác định nên gọi phương thức nào.

-- Tại sao sử dụng tính kế thừa trong Java?

+) Để ghi đè phương thức (Method Overriding), do đó có thể thu được tính đa hình tại runtime.

+) Để làm tăng tính tái sử dụng của code.

- ABSTRACTION

-- Trong JAVA, abstract class (lớp trừu tượng) được sử dụng để làm lớp cha, chứa các đặc điểm và hành vi chung mà các lớp con kế thừa,abstract class được sử dụng để định nghĩa các hành vi và thuộc tính chung.

-- Lớp con bắt buộc phải implement tất cả các phương thức trừu tượng của lớp cha.

-- Không thể khởi tạo đối tượng từ lớp trừu tượng.

-- Trong JAVA, một abstract method (phương thức trừu tượng) bắt buộc phải được override (ghi đè) trong các lớp con kế thừa. Phương thức trừu tượng chỉ được khai báo trong lớp cha, nhưng không có phần thân thực thi (implementation), vì vậy các lớp con cần phải cung cấp chi tiết cụ thể cho phương thức này.

-- Trong 1 lớp trừu tượng, từ khóa this vẫn có thể được sử dụng mặc dù lớp này không thể được khởi tạo trực tiếp. Điều này là do this là một tham chiếu đến đối tượng hiện tại và sẽ trỏ tới các đối tượng của bất kỳ lớp con nào kế thừa từ lớp trừu tượng đó.

-- Abstract thể hiện mối quan hệ IS-A còn Interface thể hiện mối quan hệ HAS-A.

-- Phiên bản Java < 8, Interface chỉ có thể có phương thức abstract. Phiên bản Java 8, có thể thêm default và static methods.
Phiên bản Java 9, có thể thêm private methods.

-- Interface chỉ có các biến static final.

- POLYMORPHISM

-- Tính đa hình là khả năng một đối tượng có thể thực hiện một tác vụ theo nhiều cách khác nhau.

-- Trong Java, chúng ta sử dụng nạp chồng phương thức (method overloading) và ghi đè phương thức
(method overriding) để có tính đa hình.

- COLLECTIONS

-- Iterable -> Collection -> List.

-- Iterable: Đây là Interface gốc, cung cấp phương thức iterator() để lặp qua các phần tử. Tất cả các lớp triển khai Iterable
có thể được duyệt bằng vòng lặp for-each.

-- Collection: Kế thừa Iterable và định nghĩa một tập hợp các phương thức cơ bản cho các cấu trúc dữ liệu dạng tập hợp
(collection) như thêm, xóa, kiểm tra kích thước, kiểm tra trống, và duyệt các phần tử.

-- List: Kế thừa Collection và mở rộng thêm các phương thức cụ thể cho kiểu danh sách (list), bao gồm truy cập phần tử
theo chỉ mục, tìm kiếm phần tử, thêm/xóa theo vị trí, và hỗ trợ các danh sách có thứ tự và trùng lặp.

-- List trong JAVA là 1 Interface nằm trong gói java.util. List định nghĩa một tập hợp các phương thức mà các Class
như ArrayList, LinkedList, và Vector phải implement.

-- Bất kỳ collection nào được tạo từ phương thức tĩnh of() trong các interface như List, Set, hoặc Map đều là immutable (bất biến).
Điều này có nghĩa là sau khi được khởi tạo bằng of(), collection sẽ không thể thay đổi—không thể thêm, xóa, hoặc cập nhật các phần tử

- VERTOR và ARRAYLIST

-- Cả 2 class đều implement Interface List.

-- Cả 2 class đều sử dụng cấu trúc dữ liệu Array.

-- Tất cả các phương thức (methods) của lớp Vector trong Java đều được đồng bộ hóa (synchronized).
Điều này có nghĩa là các phương thức của Vector được bảo vệ để chỉ một luồng (thread) có thể truy cập vào chúng tại một thời điểm.
Điều này giúp đảm bảo tính an toàn khi truy cập dữ liệu trong môi trường đa luồng.

- SET

-- Iterable -> Collection -> Set

-- Set (tập hợp) trong Java là một Interface, được kế thừa từ Interface Collection. Set ĐẶC BIỆT không chứa các phần tử trùng nhau.

-- Khác với Interface List, Interface Set ĐẶC BIỆT không có các phương thức thao tác với phần tử theo vị trí/chỉ mục.

-- Set định nghĩa một tập hợp các phương thức mà các Class như HashSet, LinkedHashSet và TreeSet phải implement.

-- HashSet: Không đảm bảo thứ tự của phần tử, vì nó sử dụng bảng băm (hash table) để lưu trữ.

-- LinkedHashSet: Sắp xếp thứ tự của phần tử theo thứ tự chèn.

-- TreeSet: Sắp xếp phần tử theo thứ tự tự nhiên hoặc theo Comparator tùy chỉnh.

- QUEUE

-- Iterable -> Collection -> Queue

-- QUEUE (tập hợp) trong Java là một Interface, được kế thừa từ Interface Collection và hoạt động theo cơ chế FIFO (First-In-First-Out).

-- QUEUE được sử dụng khi muốn sắp xếp mọi thứ theo thứ tự mà bạn muốn xử lý chúng.

- Map

-- Trong java, map được sử dụng để lưu trữ và truy xuất dữ liệu theo cặp khóa (key) và giá trị (value). Mỗi cặp key và value được gọi là entry.

-- Map chỉ chứa các giá trị key duy nhất, không chứa các key trùng lặp.

Các lớp triển khai (implements) Map interface là HashMap, HashTable, LinkedHashMap and TreeMap:

+) HashMap không đảm bảo thứ tự các entry được thêm vào.

+) LinkedHashMap đảm bảo thứ tự các entry được thêm vào.

+) TreeMap duy trình thứ tự các phần tử dựa vào bộ so sánh Comparator.

-- Sức chứa (compacity) mặc định khi khởi tạo map là 24 = 16. Kích thước này sẽ tự động tăng gấp đôi mỗi khi thêm phần tử vượt quá kích thước của nó.
