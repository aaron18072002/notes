@@

--- ASP.NET Core: Cả bốn công nghệ đó (ASP.NET Core MVC, ASP.NET Core Web API, ASP.NET Core Razor Pages và ASP.NET Core Blazor) đều là các module hoặc phần của ASP.NET Core framework. ASP.NET Core là một framework mạnh mẽ cho việc xây dựng ứng dụng web, và các công nghệ trên được thiết kế để cung cấp các phương tiện và tính năng khác nhau để phát triển các loại ứng dụng web khác nhau, từ ứng dụng đơn giản đến các ứng dụng phức tạp hơn. Mỗi công nghệ này cung cấp một cách tiếp cận và tính năng riêng biệt, nhưng tất cả đều được xây dựng trên cùng một nền tảng ASP.NET Core.

- ASP.NET Core MVC: Thích hợp cho việc xây dựng các ứng dụng web từ trung bình đến phức tạp, ASP.NET Core MVC cung cấp một mô hình lập trình mạnh mẽ dựa trên mô hình MVC cho việc phân tách logic ứng dụng. Đây là lựa chọn phổ biến cho các ứng dụng web có nhu cầu phức tạp về điều hướng, quản lý dữ liệu và tương tác người dùng.

- ASP.NET Core Web API: Được sử dụng để xây dựng các dịch vụ RESTful, dùng cho mọi loại ứng dụng khách. ASP.NET Core Web API là lựa chọn lý tưởng cho việc tạo các API dữ liệu cho ứng dụng web, ứng dụng di động, ứng dụng desktop và các loại ứng dụng khác. Sử dùng MVC pattern nhưng không xài Views.

- ASP.NET Core Razor Pages: Thích hợp cho việc xây dựng các ứng dụng web đơn giản, tập trung vào từng trang. ASP.NET Core Razor Pages cung cấp một cách tiếp cận trực quan và dễ dàng cho việc phát triển các ứng dụng web đơn giản mà không cần phải tạo ra cấu trúc mô hình MVC.

- ASP.NET Core Blazor: Được sử dụng để xây dựng các ứng dụng web với mã nguồn C# cả ở phía máy khách (client-side) và phía máy chủ (server-side). Blazor cho phép phát triển ứng dụng web mà không cần sử dụng JavaScript, thay vào đó sử dụng C# và .NET trên cả hai phía.

--- ViewData, ViewBag, TempData, ViewModel trong MVC

- ViewData và ViewBag đều dùng để passing data từ controller sang view. Nhưng type của ViewBag là dynamic còn type của ViewData là một KeyValuePair<string, object>.

- Cả ViewData và ViewBag đều có lifetime là 1 request. Vậy nên khi user gửi 1 request khác thì ViewData và ViewBag đều mất.

- TempData dùng để passing data trong 2 request liên tiếp. VD: Hiển thị notification khi update, create, ...

- TempData có lifetime là 1 session.

- ViewModel là 1 custom class do user tự định nghĩa để store model và các data cần thiết để ràng buộc với view nào đó. Model ở đây có thể là entity, DTO còn data có thể là ViewBag, ViewData, TempData, SelectItemList ,...

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

-- Middleware Chain: Middleware đầu tiên sẽ nhận request - ở đây là HttpContext, xử lý và gán nó cho middleware tiếp theo. Quá trình này tiếp diễn cho đến khi đi đến middleware cuối cùng. Tùy thuộc bạn muốn pipeline của bạn có bao nhiêu middleware Middleware cuối cùng sẽ trả request ngược lại cho middleware trước đó lần lượt cho tới middleware đầu tiên, và sẽ ngắt quá trình trong request pipeline.

-- Pipeline: Trong ứng dụng ASP.NET Core, các middlware kết nối lại với nhau thành một xích, middleware đầu tiên nhận HTTP Request, xử lý nó và có thể chuyển cho middleware tiếp theo hoặc trả về ngay HTTP Response. Chuỗi các middleware theo thứ tự như vậy gọi là pipeline.

-- Short-circuit middleware là các middleware trong pipeline mà có khả năng chấm dứt việc xử lý request và response trước khi đến middleware tiếp theo trong pipeline. Cụ thể, khi một short-circuit middleware quyết định rằng không cần tiếp tục xử lý, nó có thể trả về một phản hồi hoặc thậm chí không trả về gì cả, kết thúc ngay lập tức quá trình xử lý của yêu cầu.

-- Cả 2 method Run() và Use() đều dùng để tạo ra Middleware dưới dạng request delegate.

-- Method Run() không chuyển hướng request sang middleware tiếp theo ( subsequence middleware ) trong pipeline. Thay vào đó, nó là kết thúc của pipeline và kết thúc xử lý của yêu cầu, không cho phép các middleware tiếp theo trong pipeline được gọi.

-- Method Use() dùng để thực thi một short-circuiting middlware hay một non-terminating middleware. Non-terminating middleware là 1 dạng middleware mà nó có thể chuyển hướng request ( HttpContext ) sang middleware tiếp theo. Cả 2 method Run() và Use() đều là extension method với tham số đầu tiên là this IApplicationBuiilder app

- Khái niệm Middleware Class

-- Middleware Class là một cách để tách logic của middleware từ các biểu thức lambda thành các class riêng biệt, có thể tái sử dụng và dễ dàng quản lý.

- Vì sao không nên dùng Route Constraints cho việc Validator

-- Scope và Mục đích: Route constraints được thiết kế để kiểm soát các phần cụ thể của URL trong quá trình định tuyến. Chúng chỉ tập trung vào dữ liệu trong các phần của URL, nhưng validation thường đòi hỏi kiểm tra toàn bộ dữ liệu đầu vào của yêu cầu HTTP.

-- Độ Phức tạp: Route constraints thường chỉ kiểm tra giá trị của một phần cụ thể của URL. Trong khi đó, validation có thể bao gồm nhiều loại kiểm tra phức tạp như kiểm tra dạng dữ liệu, kiểm tra logic, kiểm tra ràng buộc phụ thuộc vào dữ liệu khác. Sự phức tạp này không thể được biểu diễn một cách hiệu quả thông qua route constraints.

-- Hiệu suất: Route constraints được thực thi trước khi request được xử lý bởi các middleware và controller. Nếu bạn thực hiện validation trong route constraints, điều này có thể làm tăng thời gian xử lý cho mỗi request và ảnh hưởng đến hiệu suất của ứng dụng.

-- Phân Chia Trách Nhiệm: Việc sử dụng các công cụ validation riêng biệt giúp phân chia rõ ràng trách nhiệm trong ứng dụng. Route constraints nên được sử dụng để kiểm soát việc định tuyến, trong khi validation nên được thực hiện ở các lớp hoặc phần riêng biệt của ứng dụng.

- UseRouting trong Asp.Net

-- Routing trong ASP.NET Core là 1 tiến trình mapping HTTP Request đầu vào với enpoint tương ứng bằng cách kiểm tra HTTP method và url. Nếu match, gọi enpoint tương ứng. Để kích hoạt tiến trình này, ta cần gọi UseRouting method() ở program.cs file.

-- Khi method UseRouting() được thực thi, ta kích hoạt routing middleware. Khi một HTTP Request đến, routing middleware sẽ kiểm tra URL của request và matching nó với các quy tắc định tuyến đã được cấu hình trước. Các quy tắc này định rõ cách mà các URL sẽ được ánh xạ đến các action methods cụ thể trong ứng dụng của bạn.

-- Default Route Parameter: /products/details/{id=1}

-- Optional Route Parameter: /employees/profile/{id?}

- Router Parameter Constraints

-- Ràng buộc về type: /files/filename:string

-- Ràng buộc về length: /file/filename:length(4,7)

- Các ưu tiên về quy trình lựa chọn endpoint trong routing của ASP.NET Core được sắp xếp như sau:

0. Route Parameters là case insentitive. Nghĩa là /files/{filename}.{extension} không khác gì /files/{fileName}.{EXTENSION}

1. URL Template với nhiều phân đoạn ( segments ): Khi có nhiều URL template cùng phù hợp với một URL, quy tắc này xác định rằng URL template có số lượng phân đoạn lớn hơn sẽ có ưu tiên hơn. Ví dụ, URL template "a/b/c/d" sẽ có ưu tiên hơn "a/b/c".

2. URL Template với văn bản cố định: Khi có nhiều URL template có cùng số lượng phân đoạn và một phân đoạn là văn bản cố định - literal text, URL template với văn bản cố định sẽ có ưu tiên hơn so với một phân đoạn là tham số. Ví dụ, URL template "a/b" sẽ có ưu tiên hơn "a/{parameter}".

3. URL Template có ràng buộc cho tham số: Trong trường hợp có nhiều URL template với cùng một số lượng phân đoạn và cùng một phân đoạn là tham số, URL template có ràng buộc cho tham số sẽ có ưu tiên hơn so với một tham số không có ràng buộc. Ví dụ, URL template "a/{id:int}" sẽ có ưu tiên hơn "a/{id}".

- Khái niệm Controller trong ASP.NET

-- Một controller là một lớp (class) chứa một tập hợp các phương thức hành động (action methods). Mỗi action method trong controller thường được xem như là một điểm cuối (endpoint) trong ứng dụng web của bạn.

-- Khi một HTTP request đến, ASP.NET sẽ sử dụng định tuyến (routing) để xác định controller và action method tương ứng để xử lý request đó. Controller chịu trách nhiệm xử lý logic liên quan đến request và trả về response.

-- Method MapController() internally và automatically gọi UseRouting() và UseEndpoints() methods.

-- Một Controller Class phải có chữ cuối là Controller và [Controller] attribute phải được thêm vào class đó hoặc base class của nó.

-- Khi một url matching với 1 endpoint nào đó, ASP.NET Core sẽ tự động tạo ra 1 object của Controller chứa endpoint đó.

-- Trong ASP.NET Core, các controller có lifetime mặc định là transient. Điều này có nghĩa là một instance mới của controller sẽ được tạo mỗi khi có một yêu cầu (request) đến.

- ContentResult trong ASP.NET

-- Trả về text/plain, html/text, json/text, pdf files, application/xml, ...

- Các kiểu FileResult trong ASP.NET Core

-- VirtualFileResult: Được sử dụng khi file muốn trả về nằm trong thư mục wwwroot của dự án.

-- PhysiccalFileResult: Được sử dụng khi file muốn trả về không nằm trong thư mục wwwroot, mà có thể nằm ở bất kỳ đâu trên hệ thống tệp kể cả bên ngoài project.

-- FileContentResult: Nó được sử dụng khi muốn trả về dữ liệu của tệp dưới dạng một mảng byte, thường là từ một dữ liệu đã được tạo ra trong bộ nhớ hoặc từ một nguồn dữ liệu khác (từ 1 api khác) hoặc image từ database.

- RedirectResult trong ASP.NET

-- 301: Moved/Permenantly, 302: Found/Temporary

-- RedirectToAction: Chuyển tiếp sang một action method khác trong application của ta.

-- LocalRedirectResult: Chuyển tiếp sang url mà không thuộc application của ta hoặc dùng với nhứng url phức tạp. Ví dụ: return LocalRedirectResult("google.com")

- Model Binding trong ASP.NET

-- Model Binding là một kỹ thuật cho phép tự động ánh xạ dữ liệu từ HTTP requests vào các đối tượng trong ứng dụng web của bạn.

-- Model binding giúp tự động ràng buộc (bind) dữ liệu từ nguồn dữ liệu - Request đến các thuộc tính của Model trong ứng dụng. Nó giúp giảm thiểu công việc phức tạp của việc truy xuất và gán dữ liệu một cách thủ công. Thay vì phải xử lý các thông tin đầu vào từ người dùng một cách rời rạc, model binding cho phép bạn định nghĩa các Model với các thuộc tính tương ứng và gửi dữ liệu từ nguồn dữ liệu đến các thuộc tính này một cách tự động.

-- Request Binding: Khi một HTTP request được gửi đến server, ASP.NET sẽ tự động phân tích dữ liệu từ request và cố gắng ánh xạ chúng vào các thuộc tính của đối tượng Model dựa trên tên của các trường trong request và tên của các thuộc tính trong Model. Nếu tên trường và tên thuộc tính khớp nhau, dữ liệu sẽ được ánh xạ tự động và một object của Model sẽ được tạo ra. Điều này giúp bạn tránh việc phải viết mã để thủ công lấy dữ liệu từ request và gán cho các thuộc tính của đối tượng.

-- Thứ tự nguồn dữ liệu ưu tiên mà Model Binding sẽ đọc từ Request: Form fields -> Request Body -> Route Parameters -> Query string.

- So sánh Form-Urlencoded và Form-Data

-- Trong ASP.NET, cả 2 đều được xem là Form Fields.

-- Khi số lượng fields nhiều hoặc muốn upload file thì nên dùng Form-Data vì From-Urlencoded mặc định là application/x-www-form-urlencoded trong khi của Form-Data là multipart/form-data ( có thể dùng với nhiều nguồn dữ liệu ).

- 3 Properties của ModelState - ModelState là property của ControllerBase

-- ModelState dùng để catch errors từ Model Validation Attribute.

-- IsValid: Return boolean, chỉ ra liệu có ít nhất một validation error hay không.

-- Values: Chứa các giá trị của các fields trong model sau khi đã được ánh xạ từ dữ liệu đầu vào và các errors tương ứng ( nếu có ).

-- ErrorCount: Trả về tổng số errors đã catch.

- Attribute Parameter trong Action Method

-- Bind Attribute được sử dụng để chỉ định các thuộc tính của một mô hình mà bạn muốn liên kết từ dữ liệu yêu cầu. Điều này giúp kiểm soát và giới hạn những dữ liệu nào từ người dùng sẽ được ánh xạ đến đối tượng mô hình, ngăn chặn các thuộc tính không mong muốn hoặc không an toàn khỏi việc bị ghi đè. Mặc định thì toàn bộ properties của 1 Model đều được Binded.

-- BindNever Attribute dùng chỉ định 1 field cụ thể không được Binded.

- Sự khác nhau giữa 2 methods Bind(object obj) và Get<T>() khi implement Options Pattern lúc làm việc với Configuration:

-- Get: Load values ( từ key/value pairs của Configuration ) vào 1 object mới.

-- Bind: Load values ( từ key/value pairs của Configuration ) vào 1 object đã được khai báo.

- Thứ tự mà 1 ASP.NET Core Project đọc các file Config

-- Các Configs từ User-Secrets chỉ nên dùng ở Development Env.

-- appsettings.json -> appsettings.Development.json -> User-Secrets -> Environment Variales -> Custom Configs

- Enviroment trong 1 dự án ASP.NET Core

-- Development: môi trường cho dev.

-- Staging: môi trường để testing (gần giống production).

-- Production: môi trường thực tế khách hàng sử dụng.

- [ApiController] attribute trong ASP.NET

-- Khi bạn đánh dấu một lớp với [ApiController], ASP.NET sẽ nhận biết lớp đó là một API Controller và tự động thực hiện một số công việc:

-- 1. Routing: Attribute này kích hoạt tính năng routing tự động trong ASP.NET Web API. Khi một yêu cầu HTTP được nhận, hệ thống sẽ so khớp nó với các phương thức trong lớp API Controller dựa trên các quy tắc định tuyến.

-- 2. Model Binding: Khi một yêu cầu HTTP đến, ASP.NET sẽ tự động liên kết các tham số của phương thức API Controller từ dữ liệu trong yêu cầu. Điều này bao gồm dữ liệu từ URL (query string), dữ liệu từ phần thân của yêu cầu (request body), hoặc các header HTTP.

-- 3. Validation: ASP.NET cung cấp tính năng validation tự động cho các tham số của phương thức API Controller. Khi bạn định nghĩa các quy tắc validation cho các tham số (ví dụ: yêu cầu một trường cụ thể không được trống), hệ thống sẽ tự động kiểm tra và trả về lỗi nếu dữ liệu không hợp lệ.

-- 4. Content Negotiation: Khi một phương thức API Controller trả về một đối tượng, ASP.NET sẽ tự động serialize đối tượng đó vào định dạng dữ liệu được yêu cầu. Điều này có nghĩa là nếu yêu cầu yêu cầu JSON, đối tượng sẽ được serialize thành JSON; nếu yêu cầu XML, đối tượng sẽ được serialize thành XML.

- EntityFramework Core

-- DbContext binded với database

-- DBSet là một class đại diện cho một entity(model) trong database.

-- Method Add(obj) trong DbContext chỉ thêm obj đó vào DbSet và đánh dấu nó là "Added" trong Change Tracker còn SaveChanges() mới là method mà tạo ra các câu lệnh sql để thực thi vào database. Tương tự với Remove(obj) thì là "Deleted" còn lại là "Modified".

-- Lệnh Add-Migration trong Entity Framework Core sẽ theo dõi các thay đổi trong lớp DbContext và các lớp thực thể của bạn. Khi bạn chạy Add-Migration, Entity Framework sẽ so sánh mô hình hiện tại của bạn với mô hình trước đó và tạo ra một tệp migration chứa các thay đổi cần thiết để cập nhật cơ sở dữ liệu theo mô hình mới.

-- Fluent API trong Entity Framework Core là tập hợp các phương thức được thiết kế để tác động và cấu hình các bảng (tables) trong cơ sở dữ liệu theo cách thức "method chaining". Đây là cách để lập trình viên cấu hình chi tiết các thực thể (entities) và các mối quan hệ giữa chúng một cách linh hoạt và rõ ràng.

- Logging trong ASP.NET

-- Logging là tiến trình ghi lại các sự kiện xảy ra trong ứng dụng theo thời gian thực. Mục đích của logging là lưu lại các chi tiết của lỗi như phương thức hành động (action method), dịch vụ (service), và các thông tin khác có thể giúp bạn debug và phân tích ứng dụng.

-- 5 levels của log: Debug, Information, Warning, Error, Critical.

-- HTTP Logging là 1 middleware mà ghi lại details của HTTP Request và Response ngay khi chúng xảy ra tại thời gian thực.

-- Logging provider chỉ ra nơi mà store/display log messages.

-- Có 3 Loggin Provider: Console, Debug, EventLog.

- Filter trong ASP.NET

-- Middleware hoạt động trên toàn bộ pipeline của ứng dụng, có khả năng can thiệp vào bất kỳ yêu cầu HTTP nào từ lúc bắt đầu cho đến lúc kết thúc. Middleware có thể ảnh hưởng đến mọi yêu cầu và phản hồi, bất kể yêu cầu đó liên quan đến controller nào. Các middleware thường được sử dụng cho các tác vụ như xác thực, logging, xử lý lỗi, định tuyến, và quản lý phiên làm việc.

-- Filter chỉ áp dụng cho các action trong controller. Chúng cho phép bạn can thiệp vào quá trình xử lý của một action cụ thể hoặc một nhóm các action. Các filter có thể thực hiện các tác vụ như kiểm tra quyền truy cập trước khi action chạy (Authorization Filter), thực hiện thao tác trước và sau action (Action Filter), hoặc xử lý kết quả trả về (Result Filter).

-- OnActionExecuting được thực thi trước khi action method trong controller được gọi, nhưng sau khi model binding đã hoàn tất.

-- Dưới đây là thứ tự thực thi trong pipeline của ASP.NET Core khi một yêu cầu HTTP được xử lý:

1. Middleware: Các middleware được thực thi đầu tiên khi một yêu cầu HTTP đi qua pipeline.

2. Routing Middleware: Yêu cầu được định tuyến tới controller và action method tương ứng.

3. Authorization Filters: Kiểm tra quyền truy cập. Nếu người dùng không được phép, pipeline sẽ dừng lại ở đây và trả về kết quả mà không tiếp tục.

4. Resource Filters (OnResourceExecuting): Được thực thi sau khi kiểm tra quyền truy cập, trước khi bất kỳ action method nào được thực hiện. Resource filters có thể can thiệp vào toàn bộ yêu cầu và ngăn chặn việc thực thi action method.

5. Model Binding: Dữ liệu từ yêu cầu (ví dụ như từ query string, form data) được gán vào các tham số của action method.

6. Action Filters (OnActionExecuting): Thực thi trước action method, cho phép can thiệp hoặc kiểm tra trước khi action method được gọi.

7. Action Method: Action method của controller được thực thi.

8. Action Filters (OnActionExecuted): Thực thi sau khi action method đã hoàn thành.

9. Exception Filters: Xử lý các exception (lỗi) phát sinh trong quá trình thực thi action method hoặc các filters khác. Nếu xảy ra lỗi, exception filter có thể can thiệp và cung cấp một response thay thế.

10. Resource Filters (OnResourceExecuted): Thực thi sau khi action method và các filters khác đã hoàn thành. Có thể can thiệp vào response hoặc hủy bỏ việc xử lý tiếp tục.

11. Result Filters: Xử lý kết quả trả về, như định dạng dữ liệu hoặc thay đổi response trước khi gửi về client.

12. Response: Kết quả được gửi trả về client.

-- Result Filters có hai phương thức chính: OnResultExecuting và OnResultExecuted:

1. OnResultExecuting: Thực thi trước khi result được xử lý. Tại đây, bạn có thể kiểm tra hoặc sửa đổi kết quả trước khi nó được gửi đi. Nếu cần, bạn có thể ngăn chặn việc xử lý tiếp tục bằng cách đặt kết quả khác hoặc hủy bỏ.

2. OnResultExecuted: Thực thi sau khi result đã được xử lý và gửi về client. Đây là nơi để thực hiện các thao tác hậu xử lý như ghi log hoặc giải phóng tài nguyên.

-- Result Filters chính là thứ mà tác động đến RESPONSE lần cuối trước khi nó gửi về client. Như thêm cookie, thêm response-header, ...

-- ExceptionFilters chỉ catch được Exception ở ModelBinding, ActionFilters và ActionMethods. Và không nên display exception details khi đang không ở trong môi trường Development.

-- Tất cả Filters đều implement IFilterMetadata.

-- Default lifetime của tất cả Filters là Transient.

-- Nếu dùng FilterAttribute thì Filter đó có thể là ActionFilter, ExceptionFilter, ResultFilter. Nhưng nó không support constructor DI.

-- Khi nào thì nên dùng IFilterFactory:

1. Khi bạn cần tạo Filter 1 cách flex, tùy biến theo từng tình huống cụ thể.

2. Khi bạn muốn kiểm soát vòng đời của bộ lọc hoặc tích hợp sâu hơn với hệ thống DI của ASP.NET Core.

3. Khi bộ lọc của bạn có các phụ thuộc phức tạp hoặc cần cấu hình đặc biệt.

- ApiController attribute cho Controller khi làm việc với Asp.Net API

-- Khi đã dùng [ApiController] thì bắt buộc phải dùng luôn [Route("")] nếu không sẽ throw 1 exception.

-- Nếu không dùng [ApiController] thì endpoint sẽ không nhận data từ [FromBody].

-- Khi đã dùng [ApiController] thì nếu ModelState có Error từ validation annotations nào thì Controller sẽ tự động trả về HTTP 400.

- Vì sao khi Asp.Net API project lại dùng return type là ActionResult thay vì IActionResult

-- ActionResult<T> có thể sử dụng cơ chế Generic Type để return một hoặc nhiều model types tương ứng.

-- IActionResult thì chỉ có return những type mà là con của IActionResult.

- Content Negotiation

-- Là 1 process mà khi đó ta sẽ lựa chọn format phù hợp hoặc ngôn ngữ của content để mà exchange giữa Client (brrowser) và Web Api.
