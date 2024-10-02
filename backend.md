- HTTP và HTTPS

-- HTTPS (Hypertext Transfer Protocol Secure) là một phiên bản bảo mật của giao thức HTTP (Hypertext Transfer Protocol). HTTPS sử dụng SSL (Secure Sockets Layer) hoặc TLS (Transport Layer Security) để mã hóa dữ liệu truyền từ máy khách đến máy chủ và ngược lại. SSL/TLS cung cấp một lớp bảo vệ bổ sung để đảm bảo rằng thông tin truyền qua mạng được mã hóa và không thể đọc được bởi bất kỳ ai ngoài người gửi và người nhận.

-- HTTP (Hypertext Transfer Protocol) là một giao thức truyền tải siêu văn bản, được thiết kế để trao đổi thông tin trên World Wide Web (WWW). Nó đặt ra các quy tắc cho việc truyền tải dữ liệu giữa máy khách (client), chẳng hạn như trình duyệt web, và máy chủ web (server).

- Cấu trúc của 1 HTTP Request

-- Request Line: Dòng này chứa các thông tin cơ bản về request, bao gồm: Phương thức (method): GET, POST, PUT, DELETE, ... Đường dẫn của tài nguyên được yêu cầu trên máy chủ (URI). Phiên bản của giao thức HTTP được sử dụng (ví dụ: HTTP/1.1)

-- Headers: Đây là danh sách các cặp key-value mô tả thông tin chi tiết về yêu cầu, bao gồm: User-Agent: Thông tin về trình duyệt hoặc ứng dụng gửi yêu cầu, Host: Tên miền hoặc địa chỉ IP của máy chủ mà yêu cầu đang gửi đến, Content-Type: Loại nội dung của dữ liệu gửi kèm (đối với các phương thức như POST, PUT), Content-Length: Kích thước của dữ liệu gửi kèm (nếu có),
Accept: Các định dạng dữ liệu mà client có thể chấp nhận từ server, vv.

-- Body: Đây là phần optional của request và chứa dữ liệu gửi kèm (nếu có), như dữ liệu form trong trường hợp của method POST hoặc PUT.

- Cấu trúc của 1 HTTP Response

-- Status Line: Dòng này chứa mã trạng thái HTTP và thông điệp trạng thái, bao gồm: Phiên bản của giao thức HTTP được sử dụng (ví dụ: HTTP/1.1), Status code: Đại diện cho kết quả của yêu cầu, ví dụ như 200 (OK), 404 (Not Found), 500 (Internal Server Error), ... Status message: Một thông điệp mô tả vắn tắt về mã trạng thái.

-- Header: Chứa các cặp key-value sau: Content-Type: Loại nội dung của dữ liệu được trả về, Server: Thông tin về máy chủ (phần mềm máy chủ và phiên bản), Date: Thời điểm mà phản hồi được tạo ra, Cache-Control: Các hướng dẫn về cách xử lý bộ nhớ cache.

-- Body: Phần này có thể chứa HTML, văn bản, JSON, hình ảnh, video, ... Tùy thuộc vào loại nội dung mà server trả về.

- API ( Application Programming Interface ) là gì ?

-- Là 1 tập hợp các định nghĩa và giao thức ( protocols ) để cho phép 1 application hoặc system giao tiếp với với applications hoặc systems khác. Nó cung cấp các phương thức chuẩn hóa để một ứng dụng có thể sử dụng các dịch vụ hoặc chức năng từ một ứng dụng khác mà không cần phải biết chi tiết nội bộ của nó.

- CORS

-- CORS ( Cross-Origin Resource Sharing ) là 1 tính năng được tích hợp trong HTML5 được thiết kế để giải quyết vấn Same-Origin Policy trong trình duyệt web. Same-Origin Policy là 1 cơ chế bảo mật trong trình duyệt web để ngăn các trang web truy cập data của một server khác.

-- CORS cho phép server sử dụng nó có thể cho phép hoặc chặn các requests tới server đó bằng cách thiết lập các tiêu chuẩn trong HTTP headers.

- URI và URL

-- URI ( Uniform Resource Indentifier ): Là 1 chuỗi kí tự để định danh 1 tài nguyên trên internet.

-- URL ( Uniform Resource Locator ): Là 1 dạng URI đặc biệt mà định danh cụ thể 1 tài nguyên. URL bao gồm các yếu tố như domain ( tên miền ), protocols ( http, https ), path, port, ...

- DNS

-- DNS ( Domain Name System ) là 1 hệ thống quản lý các tên miền và biến chúng thành các địa chỉ IP tương ứng trên Internet.

-- DNS cung cấp 1 cơ chế gán tên miền cho các IP tương ứng.

- Ping

-- Ping là lệnh hoặc tool được sử dụng để kiểm tra kết nối giữa local pc và 1 địa chỉ IP trên mạng.

-- Ping được sử dụng để kiểm tra liệu một server hoặc 1 địa chỉ IP có thể kết nối với máy tính của bạn hay không. Nó cũng có thể đo đạc và giám sát thời gian phản hồi (latency).

- Caching

-- Caching là cơ chế mà cho phép chúng ta có thể chứa data ở khu vực chứa tạm thời ( temporary storage area ). Nên khi lần tới chúng ta cần sử dụng data đó, data đó được get nhanh hơn.

- What is REST ?

-- REST stands for Representational State Transfer. This is a software architectural for providing standards between computer systems on the web, making it easier to communicate with each other.

-- There are 4 basic HTTP verbs used to interact with resources in a REST system:

--> GET: retrive a specifec resources ( by id ) or a collection of resources.

--> POST: create a new resource.

--> PUT: update a entire specific resource ( by id ).

--> PATCH: update a partial specific resource ( by id ).

--> DELETE: remove a specific resource by id.
