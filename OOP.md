-- OOP

-> 4 tính chất cơ bản của OOP:

--- Tính trừu tượng ( Abstraction ): Trong C#, tính trừu tượng là tiến trình ( process ) che giấu ( hiding ) các chi tiết ( underlying details ) bên trong của một object và chỉ hiển thị chức năng chính của object đó. VD: Chúng ta biết được rằng bóp phanh là xe sẽ dừng lại cho dù không biết chi tiết là xe sẽ dừng theo cơ chế nào.

--> Trong C# có thể dùng tính trừu tượng bằng abstract và interface và 2 thứ đó khác nhau như thế nào:

- Abstract class là một lớp được tạo ra với mục đích trở thành một lớp cha trong cây thừa kế, tức là khi có nhiều lớp với những đặc điểm tương tự, có thể xếp chung vào một loại, khi đó việc tạo ra một lớp chứa những đặc điểm chung và cho các lớp con thừa kế từ đó sẽ giúp bạn sử dụng lại code, dễ quản lý, áp dụng đa hình... Lớp cha có thể không đủ cụ thể để hiện thực hóa toàn bộ, do vậy một số, thậm chí có thể toàn bộ các phương thức sẽ chỉ là trừu tượng.

- Interface cũng giống như abstract class, không dùng để tạo ra các object mà dùng để tạo ra các cơ sở cho các lớp kế thửa. Nhưng khác với Abstract class, tất cả các phương thức của interface mặc định là abstract methods, vì vậy các lớp thừa kế bắt buộc phải override lại các phương thức đó ( không cần từ khóa override ). Một lớp kế thừa có thể kế thừa nhiều interface và có nghiệm vụ bắt buộc phải ghi đè lại toàn bộ các phương thức trong interface đó.

- Trong Interface should only define các methods and properties, các methods và properties của Interface không được sealed hay static. Các methods trong Interface đều là Implicit Abstract và Implicit Public. Và các devired class bắt buộc ( obligated ) phải override lại các methods đó.

- 1 abstract class có thể các fields của nó còn interface thì không.

- Methods implement interface nên là public và non-static. Bởi vì đa số những methods đó đều là các dependency.

--- Tính đóng gói ( Encapsulation ): Thể hiện việc bó ( bundling ) các methods, fields, properties vào trong 1 class cụ thể. Tính đóng gói thể hiện phạm vi và tính chất của một object. Trong C# thì tính đóng gói được thể hiện thông qua việc khai báo access modifier.

- private - phạm vi mặc định: Các private methods, properties, field Chỉ có được truy cập bên trong trong class chứa nó ( within the class they belong to ). Các methods cùng cấp trong cùng class cũng không thể gọi các private properties và private methods. Không thể truy cập được từ bên ngoài class cũng như không thể truy cập bởi các class kế thừa.

- protected: Không thể truy cập được từ bên ngoài class nhưng bên trong các class thừa kế có thể truy cập được.

- public: các thuộc tính và phương thức của class đó đều có thể được truy cập từ bên ngoài class đó bởi mọi class khác.

- internal: Truy cập bị giới hạn trong phạm vi Assembly của dự án hiện tại, nếu trong cùng assembly của dự án thì nó giống hệt như public.

- protected internal: các thuộc tính và methods của protected interal class có thể được truy cập bởi class trong cùng 1 Assembly từ các class con thừa hưởng class đó.

--- Tính kế thừa ( Inheritance ): Tính kế thừa là việc mà một class có thể tái sử dụng ( resuse ), mở rộng ( extend ) và modify các thuộc tính ( properties ) hoặc các phương thức ( methods ) của 1 class khác. Một biến của class cha ( base class ) có thể được gán lại bởi class con ( derived class ) nhưng ngược lại thì không.

--- Tính đa hình ( Polymorphism ): Tính da hình là việc nhiều thuộc tính hay phương thức có cùng tên nhưng giá trị trả về có thể khác nhau theo từng object tùy thuộc vào tham số truyền vào lúc khởi tạo. VD: 2 Object Honda và Mazda đều được khởi tạo từ class Car nhưng thuộc tính speed có thể khác nhau.

- Trong C# có 2 loại đa hình:

---> Đa hình tĩnh thể hiện qua overload method, còn đa hình động chính là override lại phương thức đó khi kế thừa.

---> C# không hỗ trợ đa kế thừa - mutilple inheritance ( nghĩa là 1 class con không thể kế thừa hơn 1 class cha - base class ).

---> So sánh đa hình động với abstract methods và virtual methods ( 1 phương thức ảo là 1 phương thức có thể bị ghi đè được ):

Giống: Đều phải khai báo virtual và abstract để có thể overide ở class thừa kế. Chỉ có thể được defined bên trong 1 abstract class. Abstract method là một empty method và chỉ chờ devired class override. Thêm nữa, chúng ta có thể không cần phải override abstract method nếu derived class cũng là 1 abstract class.

Khác: Các Class con kế thừa abstract class bắt buộc phải override abstract method ở lớp cha. Còn với virtual methods thì nếu các logic methods ở lớp cha phù hợp với lớp con rồi thì không cần phải override. Với abstract method thì chỉ có thể defined bên trong abstract class lẫn interface, còn virtual methods thì có thể được defined bên trong abstract class lẫn non-abstract class.

-- Virtual Method

- Là các method được định nghĩa trong lớp cơ sở, có thể được ghi đè ở lớp thừa kế.

-- Dependency Inversion Principle

--- Là nguyên lí cuối cùng trong SOLID, trong đó:

- Các module cấp cao không phụ thuộc vào các module cấp thấp. Cả 2 nên phụ thuộc vào interface.

- Các Class giao tiếp thông qua interface, không phải việc implement.

- VD: Với code thông thường, các module cấp cao sẽ phụ thuộc vào các module cấp thấp, tạo ra các dependency. Trong trường hợp đó, khi các module cấp thấp thay đổi thì các module cấp cao phải thay đổi theo. Dẫn đến việc code thay đổi nhiều, khó maintain.

-- Inversion of control

--- Chúng ta phải thiết kế ra 1 cơ chế mà khi ClassA cần 1 dependency thì cơ chế đó sẽ tự động bơm dependency ấy vào cho ClassA. Thì dependency ấy là gì sẽ quyết định bởi interface trong ClassA.

--- Dependency không được tạo từ bên trong lớp mà phải được inject từ bên ngoài vào.

--- IoC sẽ chịu trách nghiệm tạo ra và Dispose các instant của dependency còn tiêm nó vào module cấp cao là việc của DI.

--- Có 3 cách tiêm dependency: Constructor injection, Setter injection, Interface injection.

-- Dependency Injection

--- Dependency là gì: ClassA cần gọi 1 hàm của ClassB để hoàn thành task thì ta gọi ClassB là dependency của ClassA.

--- Là 1 kỹ thuật sử dụng da hình động ( dynamic pholymorphism ) để thực hiện hóa Inversion Of Control Pattern, nhắm giúp code của chúng ta tuân thủ theo nguyên lý Dependency Inversion.

--- DI được dùng để giảm sự phụ thuộc giữa các object, giúp chúng ta dễ dàng thay đổi code hơn, dễ maintain hơn.

--- DI thiết kế sao cho các dependency (phụ thuộc) của một đối tượng CÓ THỂ được đưa vào, tiêm vào đối tượng đó (Injection) khi nó cần tới (khi đối tượng khởi tạo)

--- 1 số thư viện hỗ trợ DI: Microsoft.Extensions.DependencyInjection, Unity, Ninjet, ...

- Các module không implement trực tiếp với nhau, mà thông qua interface. Các module cấp thấp sẽ implment interface, sau đó các module cấp cao sẽ implment các module cấp thấp thông qua interface.

--- VD: services.AddSingleton<IClassB, ClassB>();:

- Dòng này đăng ký ClassB như một dịch vụ trong container DI, nhưng thông qua interface IClassB.

- Interface IClassB cung cấp một cách để truy cập các phương thức và thuộc tính của ClassB mà không cần phụ thuộc trực tiếp vào ClassB (nguyên tắc Dependency Inversion).

- Khi một thành phần của ứng dụng yêu cầu dịch vụ IClassB, container DI sẽ cung cấp một instance của ClassB.

--- Cấu trúc DI trong ASP.NET Core

- ServiceCollection - DI Container: Là nơi cung cấp các methods như AddTrasient, AddScoped, AddSingleton để đăng kí dịch vụ hay BuildServiceProvider() để tạo 1 provider. Tự động khởi tạo các dependency và inject nó vào dịch vụ của chúng ta. Dịch vụ là lớp thực hiện các chức và dependency là lớp chứa chức năng đó.

- Service Provider: Là 1 container chứa all các services đã được đăng kí.

- Inject Dependency: Các dependencies được inject vào các controller, middleware, hoặc các thành phần khác của ứng dụng thông qua Dependency Injection. ASP.NET Core tự động quản lý việc tạo và cung cấp các dependencies này dựa trên định nghĩa và cấu hình của IServiceCollection.

--- Một hàm nhận về tham số là 1 provider và dùng provider đó để cung cấp các dịch vụ gọi là Factory.

--- Bất cứ khi nào chúng ta gọi Service - DI Container sẽ quyết định xem có tạo mới 1 instance hay sử dụng lại 1 instance trước đó. Vòng đời của Service phụ thuộc vào khi khởi tạo instance và nó tồn tại bao lâu. Có 3 mức độ vòng đời.

-- Service lifetime

- Transient: Mỗi lần Service được inject, Instance của Service đó sẽ được tạo ra. Và TransientService sẽ được Dispose tại kết thúc của scope (thường là browser request).

- Scoped: Instance được khởi tạo mỗi scope. ( Scope ở đây là mỗi lần có request đến app ). Cùng 1 request thì service sẽ được tái sử dụng. Và khi Controller trả về Response rồi thì ScopeService sẽ auto Dispose - Nên dùng cho DatabaseService.

- Singleton: Instance của service được tạo duy nhất lúc khởi chạy app và được dùng ở mọi nơi - Nên dùng cho global state.

-- Proxy và Reverse Proxy, Load Balance

- Proxy là một server trung gian nằm giữa client và server. Nhận request từ client rồi chuyển tiếp nó đến server hoặc ngược lại. Proxy đóng vai trò như một tường lửa để bảo vệ client, cung cấp một số tính năng như caching, ẩn địa chỉ IP của client.

- Reverse Proxy là một loại Proxy đặc biệt nằm trước server Back End, có nghiệm vụ bảo vệ server, có nghiệm vụ điều hướng các request tới từng server. Reverse Proxy có thể đóng vai trò như 1 Load Balancer.

- Load Balancer là một chức năng của Reverse Proxy, có nghiệm vụ phân phối các client requests hoặc network load một cách hiệu quả trên nhiều servers.

-- Clean Architecture

- Tầng Domain là tầng quan trọng nhất của kiến trúc này và nó liên quan chặt chẽ đến Entities và Use Cases. Chứa các Entities và Business Operations.

- Tầng Usecase - hay Application: phụ thuộc vào Entity và Interface còn Entity thì không phụ thuộc vào Usecase lẫn Interface.

- Tầng Presentation:

- Tầng Infrastructer: Liên quan tới việc connect db, upload files lên clound, hoặc các external services ...
