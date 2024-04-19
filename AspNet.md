--- ASP.NET Core: Cả bốn công nghệ đó (ASP.NET Core MVC, ASP.NET Core Web API, ASP.NET Core Razor Pages và ASP.NET Core Blazor) đều là các module hoặc phần của ASP.NET Core framework. ASP.NET Core là một framework mạnh mẽ cho việc xây dựng ứng dụng web, và các công nghệ trên được thiết kế để cung cấp các phương tiện và tính năng khác nhau để phát triển các loại ứng dụng web khác nhau, từ ứng dụng đơn giản đến các ứng dụng phức tạp hơn. Mỗi công nghệ này cung cấp một cách tiếp cận và tính năng riêng biệt, nhưng tất cả đều được xây dựng trên cùng một nền tảng ASP.NET Core.

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

-- Khả năng Mở Rộng: Khi bạn cần thêm các quy tắc validation mới hoặc điều chỉnh các quy tắc hiện có, sử dụng route constraints không phải là một lựa chọn linh hoạt. Các thư viện và công cụ validation như Data Annotations hoặc Fluent Validation cung cấp khả năng mở rộng và tùy chỉnh linh hoạt hơn.

-- Hiệu suất: Route constraints được thực thi trước khi request được xử lý bởi các middleware và controller. Nếu bạn thực hiện validation trong route constraints, điều này có thể làm tăng thời gian xử lý cho mỗi request và ảnh hưởng đến hiệu suất của ứng dụng.

-- Phân Chia Trách Nhiệm: Việc sử dụng các công cụ validation riêng biệt giúp phân chia rõ ràng trách nhiệm trong ứng dụng. Route constraints nên được sử dụng để kiểm soát việc định tuyến, trong khi validation nên được thực hiện ở các lớp hoặc phần riêng biệt của ứng dụng.

- UseRouting trong Asp.Net

-- Khi method UseRouting() được thực thi, ta kích hoạt routing middleware. Khi một HTTP Request đến, routing middleware sẽ kiểm tra URL của request và matching nó với các quy tắc định tuyến đã được cấu hình trước. Các quy tắc này định rõ cách mà các URL sẽ được ánh xạ đến các phương thức xử lý cụ thể trong ứng dụng của bạn.

- Các ưu tiên về quy trình lựa chọn endpoint trong routing của ASP.NET Core được sắp xếp như sau:

0. Route Parameters là case insentitive.

1. URL Template với nhiều phân đoạn: Khi có nhiều URL template cùng phù hợp với một URL, quy tắc này xác định rằng URL template có số lượng phân đoạn lớn hơn sẽ có ưu tiên hơn. Ví dụ, URL template "a/b/c/d" sẽ có ưu tiên hơn "a/b/c".

2. URL Template với văn bản cố định: Khi có nhiều URL template có cùng số lượng phân đoạn và một phân đoạn là văn bản cố định, URL template với văn bản cố định sẽ có ưu tiên hơn so với một phân đoạn là tham số. Ví dụ, URL template "a/b" sẽ có ưu tiên hơn "a/{parameter}".

3. URL Template có ràng buộc cho tham số: Trong trường hợp có nhiều URL template với cùng một số lượng phân đoạn và cùng một phân đoạn là tham số, URL template có ràng buộc cho tham số sẽ có ưu tiên hơn so với một tham số không có ràng buộc. Ví dụ, URL template "a/{id:int}" sẽ có ưu tiên hơn "a/{id}".
