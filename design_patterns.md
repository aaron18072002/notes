-> Design pattern:

-- Design pattern là khái niệm để nói về các mô hình, kiến trúc, các kiểu thiết kế phần mềm hoặc hệ thống.

-- Có 3 loại design pattern phổ biến:

--> Creational: Bao gồm những loại patterns cung cấp solutions để tạo ra các object 1 cách linh hoạt.

--- Singleton

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

--- Adapter Design Pattern:

--- Proxy Design Pattern:

--- Facade Design Pattern:

--> Behavioral Design Patterns: Bao gồm những design patterns cung cấp các solutions để các class và object giao tiếp và tương tác với nhau. Các patterns này mô tả cách mà các class và object khác nhau liên lạc với nhau và phân chia nghiệm vụ.

--- Strategy Design Pattern:

- Định nghĩa 1 tập hợp các thuật toán giống nhau, encapsulate chúng và khiến chúng thay thế cho nhau. Strategy Pattern làm cho phần thuật toán đó độc lập khỏi client sử dụng nó.

- VẤN ĐỀ: Tạo 1 cơ chế mà khi Client gọi thì Context sẽ cho các options, Client có nghiệm vụ truyền option đó vào Context, và từ option đó Context sẽ thực hiện thuật toán.

- Context: Class nhận vào instance của class mà implment ( triển khai ) IStrategy do client gửi vào để thực hiện mong muốn của Client.

- IStrategy: Interface mà cung cấp chức năng để Context sử dụng

- Concrete Strategy - Stratege Instance: Những Class mà implment IStrategy và ghi đè lại logic theo từng context.

- Client: Có trách nghiệm tạo ra các Strategy Instance và pass nó vào Context.

--- Observer Design Pattern:

- Pattern này định nghĩa 1 cơ chế subcription.

- Tạo ra mối quan hệ 1 - nhiều giữa các object với nhau, để cho khi 1 object thay đổi trạng thái hoặc event của nó thì các objects phụ phuộc vào object đó sẽ được notify và update 1 cách tự động.

- Subject - Observable: Observable class có nghiệm vụ hold các List Observer và các methods.

- Subcriber: là interface nằm trong Observable Class để nó notify cho Observers mỗi khi có state thay đổi hoặc có event nào đó.

- Observers:

VẤN ĐỀ: Chúng ta làm việc với 1 component có nghiệm vụ fetch và update database. Và component đó có thể được dùng bởi nhiều applications. Có khả năng ràng nếu 1 application update database thì các applications khác vẫn sẽ dùng database cũ. Observer Pattern sẽ khắc phục điều này. Lúc này thì component đóng vai trò 1 như 1 subject, có nghiệm vụ noitifies các applications bất cứ khi nào mà state thay đổi.

VẤN ĐỀ: Tạo 1 class hệ thống an ninh cho 1 building ( observable ) và class nhân viên bảo vệ ( observer ) sẽ phụ thuộc vào class đó. Observable Class này sẽ chứa 2 List là externalVisitor ( khách ) và observer ( nvien ) và các methods để mỗi khi xác nhận khách ra hoặc vào sẽ notify cho các observers ( nvien ) biết.

--- Command Design Pattern:

--- Chain Of Responsibility Pattern:
