---  ASP.NET Core: Cả bốn công nghệ đó (ASP.NET Core MVC, ASP.NET Core Web API, ASP.NET Core Razor Pages và ASP.NET Core Blazor) đều là các module hoặc phần của ASP.NET Core framework. ASP.NET Core là một framework mạnh mẽ cho việc xây dựng ứng dụng web, và các công nghệ trên được thiết kế để cung cấp các phương tiện và tính năng khác nhau để phát triển các loại ứng dụng web khác nhau, từ ứng dụng đơn giản đến các ứng dụng phức tạp hơn. Mỗi công nghệ này cung cấp một cách tiếp cận và tính năng riêng biệt, nhưng tất cả đều được xây dựng trên cùng một nền tảng ASP.NET Core.

- ASP.NET Core MVC: Thích hợp cho việc xây dựng các ứng dụng web từ trung bình đến phức tạp, ASP.NET Core MVC cung cấp một mô hình lập trình mạnh mẽ dựa trên mô hình MVC cho việc phân tách logic ứng dụng. Đây là lựa chọn phổ biến cho các ứng dụng web có nhu cầu phức tạp về điều hướng, quản lý dữ liệu và tương tác người dùng.

- ASP.NET Core Web API: Được sử dụng để xây dựng các dịch vụ RESTful, dùng cho mọi loại ứng dụng khách. ASP.NET Core Web API là lựa chọn lý tưởng cho việc tạo các API dữ liệu cho ứng dụng web, ứng dụng di động, ứng dụng desktop và các loại ứng dụng khác. Sử dùng MVC pattern nhưng không xài Views.

- ASP.NET Core Razor Pages: Thích hợp cho việc xây dựng các ứng dụng web đơn giản, tập trung vào từng trang. ASP.NET Core Razor Pages cung cấp một cách tiếp cận trực quan và dễ dàng cho việc phát triển các ứng dụng web đơn giản mà không cần phải tạo ra cấu trúc mô hình MVC.

- ASP.NET Core Blazor: Được sử dụng để xây dựng các ứng dụng web với mã nguồn C# cả ở phía máy khách (client-side) và phía máy chủ (server-side). Blazor cho phép phát triển ứng dụng web mà không cần sử dụng JavaScript, thay vào đó sử dụng C# và .NET trên cả hai phía.

--- Kestrel trong ASP.NET Core

- Kestrel là server http đa nền tảng mặc định cho ASP.NET Core application.

- Developer thường dùng Kestrel như 1 development server. Và sẽ dùng Reverse Proxy Servers như IIS, Nginx, Apache cho production server.

--- Profile trong file launchSettings.json

- Trong ASP.NET Core, tệp launchSettings.json là một tệp cấu hình cho việc khởi động ứng dụng trong quá trình phát triển. Nó chứa các cài đặt cho việc chạy và gỡ lỗi ứng dụng trong môi trường phát triển cụ thể.

- Một trong những phần quan trọng trong tệp launchSettings.json là phần "profiles". Mỗi profile trong mục "profiles" định nghĩa một cách cấu hình cụ thể cho việc chạy hoặc gỡ lỗi ứng dụng. Mỗi profile có thể định nghĩa các thông số như port được sử dụng, URL cụ thể, cài đặt gỡ lỗi, tham số môi trường, và nhiều thông số khác.

- Khái niệm Middleware và Pipeline trong ASP.NET Core

-- Request pipeline là một cơ chế xử lý một request đầu vào và kết thúc với đầu ra là một response. Pipeline chỉ ra cách mà ứng dụng phản hồi với HTTP Request.

-- Middleware là thành phần của phần mềm đóng vai trò tác động vào request pipeline (luồng request) để xử lý chúng và tạo ra response phản hồi lại client. Mỗi một middleware thao tác với các request nhận được từ middleware trước nó. Nó cũng có thể quyết định gọi middleware tiếp theo trong pipeline hoặc trả về response cho middleware ngay trước nó. Middleware có thể là 1 request delegate ( anonymous method hoặc lambda express ) hoặc 1 class.

-- Request delegate là 1 delegate nhận về 1 tham số kiểu HttpContext và trả về một Task.

-- Middleware trong ASP.NET Core thường không thực thi cho đến khi nó nhận được một đối tượng HttpContext. HttpContext chứa tất cả thông tin về một yêu cầu HTTP cụ thể, bao gồm các đối tượng Request, Response và các thông tin khác như các route được khớp, session, user, và các đối tượng khác liên quan đến yêu cầu và phản hồi.

-- Pipeline: Trong ứng dụng ASP.NET Core, các middlware kết nối lại với nhau thành một xích, middleware đầu tiên nhận HTTP Request, xử lý nó và có thể chuyển cho middleware tiếp theo hoặc trả về ngay HTTP Response. Chuỗi các middleware theo thứ tự như vậy gọi là pipeline.

-- Short-circuit middleware là các middleware trong pipeline mà có khả năng chấm dứt việc xử lý request và response trước khi đến middleware tiếp theo trong pipeline. Cụ thể, khi một short-circuit middleware quyết định rằng không cần tiếp tục xử lý, nó có thể trả về một phản hồi hoặc thậm chí không trả về gì cả, kết thúc ngay lập tức quá trình xử lý của yêu cầu.

-- Method Run() không chuyển hướng request sang middleware tiếp theo ( subsequence middleware ) trong pipeline. Thay vào đó, nó là kết thúc của pipeline và kết thúc xử lý của yêu cầu, không cho phép các middleware tiếp theo trong pipeline được gọi.

-- Method Use() dùng để thực thi một short-circuiting middlware hay một non-terminating mà nó có thể chuyển hướng request ( HttpContext ) sang middleware tiếp theo. Cả 2 method Run() và Use() đều là extension method với tham số đầu tiên là this IApplicationBuiilder app

- Khái niệm Middleware Class

-- Middleware Class là một cách để tách logic của middleware từ các biểu thức lambda thành các class riêng biệt, có thể tái sử dụng và dễ dàng quản lý.

- Vì sao không nên dùng Route Constraints cho việc Validator

-- Scope và Mục đích: Route constraints được thiết kế để kiểm soát các phần cụ thể của URL trong quá trình định tuyến. Chúng chỉ tập trung vào dữ liệu trong các phần của URL, nhưng validation thường đòi hỏi kiểm tra toàn bộ dữ liệu đầu vào của yêu cầu HTTP.

-- Độ Phức tạp: Route constraints thường chỉ kiểm tra giá trị của một phần cụ thể của URL. Trong khi đó, validation có thể bao gồm nhiều loại kiểm tra phức tạp như kiểm tra dạng dữ liệu, kiểm tra logic, kiểm tra ràng buộc phụ thuộc vào dữ liệu khác. Sự phức tạp này không thể được biểu diễn một cách hiệu quả thông qua route constraints.

-- Hiệu suất: Route constraints được thực thi trước khi request được xử lý bởi các middleware và controller. Nếu bạn thực hiện validation trong route constraints, điều này có thể làm tăng thời gian xử lý cho mỗi request và ảnh hưởng đến hiệu suất của ứng dụng.

-- Phân Chia Trách Nhiệm: Việc sử dụng các công cụ validation riêng biệt giúp phân chia rõ ràng trách nhiệm trong ứng dụng. Route constraints nên được sử dụng để kiểm soát việc định tuyến, trong khi validation nên được thực hiện ở các lớp hoặc phần riêng biệt của ứng dụng.

- UseRouting trong Asp.Net

-- Routings trong ASP.NET Core được dùng để map URL của request tới controller actions.

-- Khi method UseRouting() được thực thi, ta kích hoạt routing middleware. Khi một HTTP Request đến, routing middleware sẽ kiểm tra URL của request và matching nó với các quy tắc định tuyến đã được cấu hình trước. Các quy tắc này định rõ cách mà các URL sẽ được ánh xạ đến các action methods cụ thể trong ứng dụng của bạn.

- Các ưu tiên về quy trình lựa chọn endpoint trong routing của ASP.NET Core được sắp xếp như sau:

0. Route Parameters là case insentitive.

1. URL Template với nhiều phân đoạn: Khi có nhiều URL template cùng phù hợp với một URL, quy tắc này xác định rằng URL template có số lượng phân đoạn lớn hơn sẽ có ưu tiên hơn. Ví dụ, URL template "a/b/c/d" sẽ có ưu tiên hơn "a/b/c".

2. URL Template với văn bản cố định: Khi có nhiều URL template có cùng số lượng phân đoạn và một phân đoạn là văn bản cố định, URL template với văn bản cố định sẽ có ưu tiên hơn so với một phân đoạn là tham số. Ví dụ, URL template "a/b" sẽ có ưu tiên hơn "a/{parameter}".

3. URL Template có ràng buộc cho tham số: Trong trường hợp có nhiều URL template với cùng một số lượng phân đoạn và cùng một phân đoạn là tham số, URL template có ràng buộc cho tham số sẽ có ưu tiên hơn so với một tham số không có ràng buộc. Ví dụ, URL template "a/{id:int}" sẽ có ưu tiên hơn "a/{id}".

- Khái niệm Controller trong ASP.NET

-- Một controller là một lớp (class) chứa một tập hợp các phương thức hành động (action methods). Mỗi action method trong controller thường được xem như là một điểm cuối (endpoint) trong ứng dụng web của bạn.

-- Khi một HTTP request đến, ASP.NET sẽ sử dụng định tuyến (routing) để xác định controller và action method tương ứng để xử lý request đó. Controller chịu trách nhiệm xử lý logic liên quan đến request và trả về response.

-- Method MapController() internally và automatically gọi UseRouting() và UseEndpoints() methods.

-- Một Controller Class phải có chữ cuối là Controller và [Controller] attribute phải được thêm vào class đó hoặc base class của nó.

- Các kiểu FileResult trong ASP.NET Core

-- VirtualFileResult: Được sử dụng khi file muốn trả về nằm trong thư mục wwwroot của dự án.

-- PhysiccalFileResult: Được sử dụng khi file muốn trả về không nằm trong thư mục wwwroot, mà có thể nằm ở bất kỳ đâu trên hệ thống tệp kể cả bên ngoài project.

-- FileContentResult: Nó được sử dụng khi muốn trả về dữ liệu của tệp dưới dạng một mảng byte, thường là từ một dữ liệu đã được tạo ra trong bộ nhớ hoặc từ một nguồn dữ liệu khác (từ 1 api khác).

- Model Binding trong ASP.NET

-- Model Binding là một kỹ thuật cho phép tự động ánh xạ dữ liệu từ HTTP requests vào các đối tượng trong ứng dụng web của bạn.

-- AddRouting():

-- Khai báo Model: Trong bước này, bạn định nghĩa một lớp (Model) đại diện cho dữ liệu mà bạn muốn ánh xạ từ request. Lớp này chứa các thuộc tính tương ứng với các trường dữ liệu bạn muốn lấy từ request.

-- Request Binding: Khi một HTTP request được gửi đến server, ASP.NET sẽ tự động phân tích dữ liệu từ request và cố gắng ánh xạ chúng vào các thuộc tính của đối tượng Model dựa trên tên của các trường trong request và tên của các thuộc tính trong Model. Nếu tên trường và tên thuộc tính khớp nhau, dữ liệu sẽ được ánh xạ tự động. Điều này giúp bạn tránh việc phải viết mã để thủ công lấy dữ liệu từ request và gán cho các thuộc tính của đối tượng.

-- Validation với Annotation:

- 3 Properties của ModelState

-- IsValid: Return boolean, chỉ ra liệu có ít nhất một validation error hay không.

-- Values: Chứa các giá trị của các fields trong model sau khi đã được ánh xạ từ dữ liệu đầu vào. Kể cả các Errors.

-- ErrorCount:

- Service trong ASP.NET

-- Service là 1 abstraction layer (middle layer) nằm giữa presentation layer - MVC (hoặc application layer) và data layer.

-- Service thường chứa các business logic: calculate logic, validation logic, access data logic...

- Sự khác nhau giữa 2 methods Bind() và Get<T>()

-- Get: Load values vào 1 object mới.

-- Bind: Load values vào 1 object đã được khai báo.

- [ApiController] attribute trong ASP.NET

-- Khi bạn đánh dấu một lớp với [ApiController], ASP.NET sẽ nhận biết lớp đó là một API Controller và tự động thực hiện một số công việc:

-- 1. Routing: Attribute này kích hoạt tính năng routing tự động trong ASP.NET Web API. Khi một yêu cầu HTTP được nhận, hệ thống sẽ so khớp nó với các phương thức trong lớp API Controller dựa trên các quy tắc định tuyến.

-- 2. Model Binding: Khi một yêu cầu HTTP đến, ASP.NET sẽ tự động liên kết các tham số của phương thức API Controller từ dữ liệu trong yêu cầu. Điều này bao gồm dữ liệu từ URL (query string), dữ liệu từ phần thân của yêu cầu (request body), hoặc các header HTTP.

-- 3. Validation: ASP.NET cung cấp tính năng validation tự động cho các tham số của phương thức API Controller. Khi bạn định nghĩa các quy tắc validation cho các tham số (ví dụ: yêu cầu một trường cụ thể không được trống), hệ thống sẽ tự động kiểm tra và trả về lỗi nếu dữ liệu không hợp lệ.

-- 4. Content Negotiation: Khi một phương thức API Controller trả về một đối tượng, ASP.NET sẽ tự động serialize đối tượng đó vào định dạng dữ liệu được yêu cầu. Điều này có nghĩa là nếu yêu cầu yêu cầu JSON, đối tượng sẽ được serialize thành JSON; nếu yêu cầu XML, đối tượng sẽ được serialize thành XML.

- EntityFramework Core

-- DbContext binded với database

-- DbSet binded với một table cụ thể.

- Mapping Kiểu Dữ Liệu C# Sang Kiểu Dữ Liệu SQL Server

-- byte -> TINYINT

-- short -> SMALLINT

-- int -> INT

-- long -> BIGINT

-- float -> REAL

-- double -> FLOAT

-- decimal -> DECIMAL

-- bool -> BIT

-- char -> CHAR(1)

-- string -> NVARCHAR(MAX) (mặc định), hoặc NVARCHAR(độ dài)

-- byte[] -> VARBINARY(MAX), VARBINARY(độ dài), hoặc IMAGE

-- Guid -> UNIQUEIDENTIFIER

-- Enum -> INT (mặc định), hoặc kiểu cơ bản của enum

-- DateTime -> DATETIME

--DateTimeOffset -> DATETIMEOFFSET

-- TimeSpan -> TIME

-- DateOnly (C# 10) -> DATE

-- TimeOnly (C# 10) -> TIME

- Logging trong ASP.NET

-- Logging là tiến trình ghi lại các sự kiện xảy ra trong ứng dụng theo thời gian thực. Mục đích của logging là lưu lại các chi tiết của lỗi như phương thức hành động (action method), dịch vụ (service), và các thông tin khác có thể giúp bạn debug và phân tích ứng dụng.

--HTTP Logging là tiến trình ghi lại details của HTTP Request và Response ngay khi chúng xảy ra tại thời gian thực. 

-- Logging provider chỉ ra nơi mà store/display logs.

- What is Entity Framework?

-- Working with databases can often be rather complicated. You have to manage database connections, convert data from your application to a format the database can understand, and handle many other subtle issues. The .NET ecosystem has libraries you can use for this, such as ADO.NET. However, it can still be complicated to manually build SQL queries and convert the data from the database into C# classes back and forth. EF, which stands for Entity Framework, is a library that provides an object-oriented way to access a database. It acts as an object-relational mapper, communicates with the database, and maps database responses to .NET classes and objects. Entity Framework (EF) Core is a lightweight, open-source, and cross-platform version of the Entity Framework.

-- Here are the essential differences between the two:

-- Cross-platform: We can use EF Core in cross-platform apps that target .NET Core. EF 6.x targets .NET Framework, so you’re limited to Windows.

-- Performance: EF Core is fast and lightweight. It significantly outperforms EF 6.x.

- What is SQL injection attack?

-- A SQL injection attack is an attack mechanism used by hackers to steal sensitive information from the database of an organization. It is the application layer (means front-end) attack which takes benefit of inappropriate coding of our applications that allows a hacker to insert SQL commands into your code that is using SQL statement.

-- SQL Injection arises since the fields available for user input allow SQL statements to pass through and query the database directly. SQL Injection issue is a common issue with an ADO.NET Data Services query.

- How to handle SQL injection attacks in Entity Framework?

-- Entity Framework is injection safe since it always generates parameterized SQL commands which help to protect our database against SQL Injection.

-- A SQL injection attack can be made in Entity SQL syntax by providing some malicious inputs that are used in a query and in parameter names. To avoid this one, you should never combine user inputs with Entity SQL command text.

- What are POCO classes?

-- The term POCO does not mean to imply that your classes are either plain or old. The term POCO simply specifies that the POCO classes don’t contain any reference that is specific to the entity framework or .NET framework.

-- Basically, POCO (Plain Old CLR Object) entities are existing domain objects within your application that you use with Entity Framework.

- What is the proxy object?

-- An object that is created from a POCO class (model class) to support change tracking and lazy loading, is known as a proxy object.

-- There are some rules for creating a proxy class object:

1. The class must be public and not sealed.

2. Each navigation property must be marked as virtual.

3. Each property must have a public getter and setter.

3. Any collection navigation properties must be typed as ICollection <T>.

- What are the various Entity States in EF?

-- Each and every entity has a state during its lifecycle which is defined by an enum (EntityState) that have the following values:

1. Added

2. Modified

3. Deleted

4. Unchanged

5. Detached

- What are various approaches in Code First for model designing?

-- POCO model classes with data annotations

-- POCO model classes with FluentAPI in DbContext

-- In Entity Framework Code First approach, our POCO classes are mapped to the database objects using a set of conventions defined in Entity Framework. If you do not want to follow these conventions while defining your POCO classes, or you want to change the way the conventions work then you can use the fluent API or data annotations to configure and to map your POCO classes to the database tables. There are two approaches, which you can use to define the model in EF Code First:

- What is Migrations History Table?

-- In EF Core, Migrations history table (__MigrationHistory) is a part of the application database and used by Code First Migrations to store details about migrations applied to a database. This table is created when you apply the first migration to the database. This table stores metadata describing the schema version history of one or more EF Code First models within a given database.

- How you apply code first migrations through code in EF Core?

-- Entity Framework Core supports “Migrate()” method, which can be called anywhere either in controller or in any other middleware when you want to perform code first migrations programmatically instead of applying migrations using “Update-Database” command.

-- Eg:

using (var context = new MyDbContext(...))
{
    context.Database.Migrate();
}
