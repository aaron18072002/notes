-> Design pattern:

-- Design pattern là khái niệm để nói về các mô hình, kiến trúc, các kiểu thiết kế phần mềm hoặc hệ thống.

-- Có 3 loại design pattern phổ biến:

--> Creational: Bao gồm những loại patterns cung cấp solutions để tạo ra các object 1 cách linh hoạt.

--- Singleton: Singleton Pattern đảm bảo rằng một class chỉ có duy nhất 1 instance được khởi tạo và cung cấp phương thức truy cập tới instance đó từ mọi nơi trong app ( global access ).

VẤN ĐỀ:

--- Factory Method: Factory method cung cấp interface mà trong đó định nghĩa các methods cho việc tạo ra các object nhưng nó cho phép các subclasses ( lớp con ) có thể thay đổi type của object mà nó tạo ra theo các business logic cụ thể.

Cấu trúc của một Factory Method:

- Super Class: 1 Super Class trong Factory Method có thể là 1 interface hay đơn giản là 1 class thông thường.

- Sub Classes: Các class con mà implement các methods của Super Class với các tham số khác nhau theo từng nghiệp vụ của nó.

- Factory Class: 1 Class chịu trách nghiệm khởi tạo các object dựa theo params ( các tham số đầu vào ). Class này sẽ cung cấp 1 method dành cho việc khởi tạo và truy xuất object.

VD: Giả sử chúng ta có 1 ứng dụng quản lý giao thông. Nhưng ứng dụng đó chỉ có thể tạo ra các object từ class Car dẫn đến việc ứng dụng của chúng ta chỉ có thể handle các request từ đường bộ. Nhưng sau đó khách hàng muốn ứng dụng chúng ta handle thêm các request từ đường biển. Nếu như dùng if else mỗi lần tạo ra các object mới thì sẽ bị tình trạng lặp code và không linh hoạt.

--- Abstract Factory

--- Builder

--- Prototype

--> Structural Design Patterns: Bao gồm những design patterns dùng để quản lý cấu trúc của các Class and interface cũng như quản lí các mối quan hệ giữa các Class với nhau.

--- Decorater Design Pattern:

- Cung cấp những solutions để tự động thêm ( dynamically adds ) các chức năng mới vào một object hiện có mà không làm ảnh hưởng tới behavior của các object khác trong cùng base class.

- Decorater Pattern giúp code của chúng ta followed theo Open-Closed Principle.

- Component Interface (Interface hoặc abstract class): Định nghĩa giao diện cho đối tượng cơ bản và các đối tượng được mở rộng. Đây có thể là một interface hoặc một lớp abstract.

- Concrete Component (Lớp cơ bản): Triển khai giao diện được xác định bởi Component Interface. Đây là đối tượng gốc mà chúng ta muốn mở rộng hoặc thêm các chức năng mới.

- Decorator (Lớp trừu tượng Decorator): Là một lớp trừu tượng (abstract class) triển khai cùng giao diện như Component Interface. Decorator chứa một tham chiếu đến đối tượng của Component Interface và thêm các chức năng mới hoặc thay đổi hành vi của đối tượng gốc thông qua việc mở rộng và gọi lại phương thức của đối tượng gốc.

- Concrete Decorator (Lớp Decorator cụ thể): Triển khai Decorator, thêm các chức năng mới hoặc thay đổi hành vi của đối tượng gốc.

- Nói dễ hiểu thì 1 lớp Decorater là 1 lớp dùng để thêm method của 1 lớp mà cùng kiểu dữ liệu với lớp Decorater luôn ( Nghĩa là cả 2 lớp để implement 1 interface hoặc cùng thừa kế 1 class cha ).

--- Flyweight Design Pattern:

- Flyweight Design Pattern được sử dụng để tối ưu hóa việc sử dụng bộ nhớ bằng cách chia sẻ data nhiều nhất có thể trong nhiều object giống nhau. Bằng cách này, Flyweight giúp giảm lượng bộ nhớ được sử dụng trong ứng dụng bằng cách loại bỏ sự lặp lại của dữ liệu trong các đối tượng.

--> Behavioral Design Patterns: Bao gồm những design patterns cung cấp các solutions để các class và object giao tiếp và tương tác với nhau. Các patterns này mô tả cách mà các class và object khác nhau liên lạc với nhau và phân chia nghiệm vụ.

--- Strategy Design Pattern:

- Định nghĩa 1 tập hợp các thuật toán, encapsulate chúng trong 1 interface và khiến chúng thay thế cho nhau tùy thuộc vào yêu cầu của Client. Strategy Pattern làm cho phần thuật toán đó độc lập khỏi client sử dụng nó.

- VẤN ĐỀ: Tạo 1 cơ chế mà khi Client gọi thì Context sẽ cho các options, Client có nghiệm vụ truyền 1 trong các options đó vào Context, và từ option đó Context sẽ thực hiện thuật toán phù hợp.

- Context: Class chứa instance của class mà implment IStrategy và dùng instance đó để thực hiện mong muốn của Client.

- IStrategy: Interface mà cung cấp chức năng để Context sử dụng

- Concrete Strategy: Những Class mà implment IStrategy và ghi đè lại logic theo từng context. Concrete Strategy sẽ được tạo ra ở thời điểm run-time.

- Client: Có trách nghiệm tạo ra các Strategy Instance và pass nó vào Context.

--- Observer Design Pattern:

- Pattern này định nghĩa 1 cơ chế subcription.

- Tạo ra mối quan hệ 1 - nhiều giữa các object với nhau, để cho khi 1 object thay đổi trạng thái hoặc event của nó thì các objects phụ phuộc vào object đó sẽ được notify và update 1 cách tự động.

- Subject - Observable: Đây là đối tượng mà các Observer đăng ký để nhận thông báo. Subject chứa một danh sách các Observer đã đăng ký và cung cấp các phương thức để thêm, xóa và thông báo cho các Observer khi có sự thay đổi. Khi muốn notify, Observable class chỉ đơn giản là tạo 1 method Notify() rồi lặp qua tất cả các Observers rồi cho chúng gọi method Update() với thông tin muốn thông báo.

- Observer: Đây là các đối tượng đăng ký để nhận thông báo từ Subject khi có sự thay đổi. Observer thường triển khai một phương thức được gọi là update() hoặc tương tự để xử lý thông báo từ Subject.

VẤN ĐỀ: Tạo 1 class hệ thống an ninh cho 1 building ( observable ) và class nhân viên bảo vệ ( observer ) sẽ phụ thuộc vào class đó. Observable Class này sẽ chứa 2 List là externalVisitor ( khách ) và observer ( nvien ) và các methods để mỗi khi xác nhận khách ra hoặc vào sẽ notify cho các observers ( nvien ) biết.

--- Template Method Design Pattern:

- Định nghĩa một lớp cơ sở (base class) chứa phương thức template, trong đó mỗi bước của thuật toán được xác định như là một phương thức trừu tượng hoặc phương thức ảo (virtual method).

- Mỗi lớp con (sub class) có thể implment các abstract method, điều này cho phép nó tùy chỉnh hành vi của các bước của thuật toán.

- Trong quá trình chạy, lớp cơ sở gọi các phương thức được định nghĩa trong template của mình, và các lớp con sẽ cung cấp hành động cụ thể cho mỗi phương thức.

--- Chain Of Responsibility Pattern:
