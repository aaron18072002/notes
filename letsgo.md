-- C#

-> C# là gì ?

--- C# là một ngôn ngữ lập trình hướng đối tượng bậc cao do microsoft tạo ra.

--- C# là một ngôn ngữ biên dịch, nó được convert sang bytecode trên máy ảo CLR ( Common Language Runtime ). Rồi sau đó mới chuyển sang mã máy.

--- CLR( Common Languege Runtime ) có thể xem như 1 máy ảo, tại đó ứng dụng dựa trên .NET được thực thi.

--- CLR không phải 1 trình biên dịch. Mà nó được xem như 1 môi trường thực thi code ( runtime enviroment ).

--- Các biến của C# có thể được phân loại theo vị trí của bộ nhớ.

--- Field và Property

- Field: là biến được khai báo trong class.

- Property: là 1 cặp phương thức đặc biệt dùng dể truy cập và sửa đổi giá trị của field. VD: { get; set; }

--- Có 3 kiểu dữ liệu trong C#

- Values Types ( Kiểu giá trị ): Là kiểu giá trị mà được lưu trữ dưới dạng value trong bộ nhớ. Có nghĩa là biến đó lưu trữ trực tiếp giá trị được gán ( Bool, byte, char, decimal, double, Enum, float, int, long, short and struct ).

- Reference Types ( Kiểu tham chiếu ): Không giống như kiểu giá trị, kiểu tham chiếu không lưu trữ trực tiếp giá trị của nó. Thay vào đó, nó lưu trữ địa chỉ nơi mà giá trị được giữ trong bộ nhớ. Giống như nó đang lưu trữ một con trỏ trỏ đến địa chỉ nơi biến được lưu trữ ( String, arrays, collections , classes and delegate ).

  --> Trong đó, Array là một tập hợp các giá trị có cùng kiểu dữ liệu được lưu trữ tại các vị trí liền kề nhau trong bộ nhớ.

- Pointer Types ( Kiểu con trỏ ): Nhằm mục đích lưu trữ địa chỉ của 1 con trỏ khác.

--- Có 4 loại toán tử trong C#

- Toán tử số học: ( + - nhân / % ++ -- )
- Toán tử gán: ( = += -= nhân= /= %= &= )
- Toán tử so sánh: ( == != >= <= > < )
- Toán tử logic: ( && || ! )

--- Errors trong C#

- Runtime errors: Xảy ra khi application đang chạy

- Compilation errors: Xảy ra trong quá trình biên dịch

--- Parsing trong C#

- Là tiến trình ( process ) chuyển đổi ( transform ) data type.

--- Exception trong c#

- Exception là cách mà C# trình bày ( represent ) các runtime errors

--- Solution, Project khi trong Visual Studio

- Solution là 1 collection của các Projects

--- String Interpolation và String Concatenation trong C#

- String Interpolation: $"{variable}"

- String Concatenation: " " + variable + " "

--- Có 4 kiểu class trong C#

- static class: 1 Class được xác định là static là class tĩnh, không thể tạo các object từ class đó, khi khai báo 1 static class thì yêu cầu tất cả các thuộc tính lẫn methods trong class đó cũng phải static. Static Class dùng để lưu các thông tin dùng chung cho toàn bộ app của chúng ta.

- partial class: partial class được xem như các lớp con của 1 lớp cha nào đó nằm ở nhiều file (.cs) khác nhau. Nhiều file này kết hợp thành 1 trong compile-time. Các partial class muốn liên kết thì phải có cùng tên và namespace. Giống như việc chia nhỏ 1 class cha thành nhiều class con và phân bổ chúng ở nhiều file (.cs) khác nhau.

- abstract class: Abstract có nghĩa là "dở dang, chưa hoàn thiện" -> không thể tạo các instances từ Abstract Class. Abstract class cung cấp những cơ sở để những class con có thể kế thừa và override lại các method sẵn có .Nếu trong app của chúng ta có quá nhiều Class giống nhau về thuộc tính hay method nào đó thì ta có thể tạo ra 1 Abstract Class cung cấp Abstract method để cho các Class kia có thể kế thừa và ghi đè lại Abstract Method đó để giải quyết vấn đề. ( Abstract methods tên là TinhDienTich thuộc Abstract Shape - Các Class con kế thừa Class Shape có thể override lại phương thức TinhDienTich để tính toán ).

- sealed class: Lớp này không thể được kế thừa

--- Từ khóa Static

- Static Class: 1 Class được xác định là static là class tĩnh, không thể tạo các object từ class đó, khi khai báo 1 static class thì yêu cầu tất cả các thuộc tính lẫn methods trong class đó cũng phải static. Static Class dùng để lưu các thông tin dùng chung cho toàn bộ app của chúng ta.

- Static cho thuộc tính ( properties ) và phương thức ( methods ): Hàm và biến static không thuộc về object mà thuộc về Class, chúng có thể được truy cập trực tiếp từ Class mà không cần tạo ra các instances. Static Properties sẽ trả về kết quả giống nhau cho mọi object được tạo ra tử class cha.

--- Collection trong C#

- Một collection (bộ, tập hợp) là một nhóm các đối tượng có sự liên quan đến nhau. Số đối tượng trong collect có thể thay đổi tăng giảm. Có nhiều loại collection như Stack, Queue, List, ArrayList ,HashBable, Dictionary.

- Những class mà dùng để chứa ( storage ) và truy xuất ( retrieval ) dữ liệu được gọi là các collection classes. Những class này hỗ trợ các cấu trúc dữ liệu như stacks, queues, lists, hash tables.

- Những collection classes có vai trò như cấp phát động ( dynamic allocating ) bộ nhớ cho các instances hoặc truy cập vào list các item bằng index hoặc key ( trong khi array chỉ có thể truy cập vào element bằng index ).

- Có 2 dạng Collection Classes là Non-generic và Generic

- Đặc điểm của Collection:

--> Các collection classes nằm trong System.Collections.

--> Collection trong C# cũng được support các methods được tích hợp sẵn như: sắp xếp, thêm, xóa, ...

--> Không cần khai báo kích thước cụ thể khi khởi tạo.

--> Tăng giảm số lượng phần tử 1 cách linh hoạt.

--> Lưu trữ được nhiều phần tử thuộc nhiều type khác nhau.

- 1 số các collection classes

--> ArrayList:

- Về bản chất giống như Array nhưng khi khai báo 1 Array phải thiết lập kích cỡ tính -> bộ nhớ là cố định trong khi với ArrayList kích cỡ có thể tăng giảm tùy ý.

- Kiểu dữ liệu của các elements trong Array bắt buộc phải giống nhau trong khi ArrayList có thể chứa nhiều kiểu dữ liệu.

- Kiểu dữ liệu đầu vào của ArrayList là object. Mỗi dữ liệu truyền vào luôn bị convert sang object trước khi đưa vào ArrayList.

- ArrayList chấp nhận giá trị null trong khi Array thì không. Thêm nữa, ArrayList hỗ trợ sẵn các methods và thuộc tính có sẵn như count, add() - thêm value vào cuối list, capacity(), remove() - xóa phần tử đầu tiên xuất hiện trong list ...

--> Hashtable:

- Là 1 collection lưu trữ data dưới dạng key-value và chỉ có thể được truy xuất bởi key.

- Hashtable không có các index.

- Mỗi phần từ trong Hashtable bao gồm 1 cặp key-value được C# định nghĩa là 1 DictionaryEntry.

- Có các methods và thuộc tính hỗ trợ: count, Add(), ContainsKey(), ContainsValue(), ...

--> SortedList:

- Là sự kết hợp giữa ArrayList và HashTable nên cũng được hỗ trợ các methods và thuộc tính giống như 2 collection classes đó.

- Giống như Hashtable, SortedList cũng là một collection chứa các phần tử dưới dạng key-value. Nhưng các phần tử sẽ được sắp xếp theo key. Việc sắp xếp đó sẽ được tự động mỗi khi thêm 1 phần tử khác vào.

- Có thể truy xuất giá trị từ key lẫn index.

--> Stack:

- Trong C# thì Stack là 1 collection và là 1 kiểu cấu trúc dữ liệu hoạt động theo cơ chế ( LIFO - Last In First Out ). Nó không thể truy xuất phần tử theo index.

- Thêm phần tử gọi là Push ( Đẩy vào ), Lấy phần tử gọi là Pop ( Đẩy ra - lấy phần tử được thêm vào cuối cùng ).

- Được hỗ trợ các methods như:

Peek() - Trả về phần tử trên cùng trong Stack.

Pop() - Trả về phần tử trên cùng trong Stack và xóa phần tử đó khỏi Stack.

Push(object Value) - Thêm 1 phần tử vào đầu Stack. Và còn nhiều methods khác ...

--> Queue:

- Trong C# thì Queue là 1 collection và là 1 kiểu cấu trúc dữ liệu hoạt động theo cơ chế ( FIFO - First In First Out ). Là 1 danh sách lưu trữ các đối tượng nhưng không thể truy xuất các đối tượng đó theo index.

- Thêm phần tử vào Queue gọi là Enqueue ( xếp hàng ), Lấy phần tử ra khỏi Queue gọi Dequeue ( ra khỏi hàng ) và luôn luôn lấy phần tử được thêm vào đầu tiên.

- Hỗ trợ các methods như Enqueue(), Dequeue(), so on and so forth

--> BitArray:

- Trong C# BitArray là 1 collection lưu trữ các phần tử dưới dạng các bit ( 0 và 1 ) và được biểu diễn như kiểu Boolean. Trong đó true là 1 bit và false là 0 bit. Giá trị mặc định của các phần tử BitArray là false.

- Nên dùng BitArray thay cho các đổi tượng kiểu bool là vì mỗi phần tử trong BitArray chỉ tốn 1 bit, trong khi kiểu bool chỉ lưu 2 giá trị là true hoặc false nhưng lại tốn đến 1 bytes cho mỗi biến.

--> List:

- List là 1 Generic Collection, là sự kết hợp giữa ArrayList và Generic.

- Không như ArrayList, List là Collection Class bắt buộc phải chỉ định kiểu đầu vào khi muốn tạo 1 instance.

--> Dictionary

- Lớp Dictionary<Tkey,TValue> khá giống SortedList, Dictionary được thiết kế với mục đích tăng hiệu quả với tập dữ liệu lớn, phức tạp.

- Có thể truy cập đến các phần tử Dictionary thông qua key lẫn index. Không cho phép trùng key

--> HashSet

- HashSet là tập hợp các phần tử không cùng giá trị.

- Dùng để giải quyết các bài toán liên quan tới phép giao, phép hợp.

--- Generic trong C#

- Generic trong C# là một tính năng trong C#. Trong đó kiểu dữ liệu ( của biến, tham số, kiểu trả về của các methods ) được xác định ở giai tạo khởi tạo.

- Generic allow to define generic classes, interface, abstract classes, fields, methods, events, delegates using Type Parameter without specific data type. A type parameter is a placeholder for paritucal type specified ( type được chỉ định cụ thể ) when create an instance of the generic type.

--- Anonymous Type ( Kiểu vô danh )

- Được khai báo bằng từ khóa new { }.

- Read-only, không thể modify các biến trong kiểu vô danh.

--- Sự khác biệt giữa late binding và early binding trong C#

- Late binding và early binding là ví dụ về tính đa hình trong OOP

- Early binding: xảy ra tại thời điểm biên dịch. Nó kiểm tra các methods và thuộc tính của static class.

VÍ DỤ: khi gọi 1 method từ 1 object, early binding sẽ kiểm tra rằng method đó tồn tại và có thể được gọi từ đối tượng đó hay không.

- Late binding: xảy ra tại thời điểm runtime. Late binding xảy ra khi đối tượng là 1 dynamic type. Biến kiểu động - ngầm định - khai báo với từ khóa dynamic, type của biến dynamic type được xác định tại thời điểm runtime ( khác với var - type được xác định tại thời điểm biên dịch ).

--- Mutex trong C#

- Trong multithreading, Mutex là 1 cơ chế đồng bộ hóa được sử dụng để đảm bảo rằng chỉ có 1 luồng ( thread ) có thể truy cập vào 1 tài nguyên cụ thể tại 1 thời điểm cụ thể. Mutex được sử dụng để tránh conflict thread và đảm bảo dữ liệu được truy cập 1 cách an toàn.

--- Overloading và Override

Cả 2 đều là những kỹ thuật giúp tạo nên tính đa hình ( Polymorphism )

Overloading - Nạp chồng: Kỹ thuật tạo ra các methods có cùng tên nhưng giá trị trả về lại khác nhau tại các ngữ cảnh khác nhau. Chỉ có method main() là không được nạp chồng.

Để implement overloading trong C#:

- Thay đổi số lượng tham số

- Thay đổi thứ tự tham số

- Sử dụng type khác nhau cho tham số

Override: Ghi đè lại method ở class cha mà class con kế thừa

--- Namespace trong C#

- Namespace là một keyword được dùng để khai báo ( declare ) 1 phạm vi chứa một tập hợp ( a set ) các class, struct chúng ta muốn lưu trữ trong namespace đó.

--- Explicit Conversion trong C#

- Chuyển đổi ngầm trong C# sẽ được auto implment khi mà chúng ta convert 1 data type sang 1 data type lớn hơn.

--- String và StringBuilder trong C#

- String là đối tượng immutable. Nghĩa là mỗi lần thao tác với 1 String, C# sẽ tự động tạo ra 1 String mới trong memory,

- StringBuilder allow bạn change 1 chuỗi trực tiếp trong memory thay vì tạo 1 bản copy mới. Default size của 1 StringBuilder là 16 nhưng nó có thể update 1 cách tự động.

--- Sự khác biệt giữa cách truyền tham số ref và out

- Cả 2 đều được dùng để truyền tham chiếu tới hàm.

- Biến truyền vào với keyword out không cần phải khởi tạo giá trị ban đầu. Vậy nên biến out chỉ dùng để xuất giá trị ra thôi.

--- So sánh toán tử == và equals()

- Cả 2 đều trả về true, false.

- Toán tử == sẽ so sánh điểm tham chiếu của biến được so sánh.

- Phương thức equals() dùng để so sánh giá trị được mang bởi các đối tượng.

--- Constructor trong C#

- Một method khởi tạo có cùng tên với class cha của nó.

- Có nghiệm vụ khởi tạo giá trị cho các thuộc tính trong class hoặc nhận giá trị đầu vào và gán các trị đó vào các thuộc tính.

--- Từ khóa this

- This dùng để tham chiếu ( references ) - ánh xạ đến đối tượng hiện tại.

- public Animal(string name, string sound) : this(name) - this(name) ám chỉ việc gọi 1 constructor khác cùng class nơi mà chỉ nhận 1 tham số là name.

--- Struct trong C#

- Struct như 1 custom type do chúng ta tự định nghĩa với fields và methods giống như 1 class.

- Struct là 1 value type, nó lưu trữ giá trị trực tiếp của nó trong memory.

- Struct khác với class là nó không thể được kế thừa.

--- So sánh Const và ReadOnly trong C#

- Const là 1 compile-time constant cũng như 1 implicitly static. Biến const bắt buộc phải được gán giá trị lúc khai báo và không thể modify. Type của const được xác định ở thời điểm biên dịch.

- ReadOnly là 1 runtime constant. Biến ReadOnly có thể được gán giá trị lúc khai báo hoặc trong constructor. Type của readOnly được xác định ở thời điểm khởi tạo.

- Const áp dụng với basic type, string và 1 số type mà không thể modify tại thời điểm biên dịch.

- ReadOnly áp dụng được cho tham chiếu lẫn tham trị trừ Delegate và event.

--- Từ khóa null

- null là từ khóa ám chỉ rằng nó không tham chiếu tới đối tượng nào cả.

--- Delegate trong C#

- Delegate trong C# là một kiểu dữ liệu đặc biệt để khai báo biến tham chiếu trỏ tới địa chỉ các hàm hoặc methods. Với điều kiện là các hàm và methods đó có cùng kiểu dữ liệu trả và cùng kiểu dữ liệu tham số đầu vào.

- Một biến delegate có thể gọi nhiều function hay nhận 1 chuỗi các tham chiếu liên tiếp gọi là multicast, một function có thể được gọi nhiều lần. Những functions đó được implment 1 cách tuần tự.

- Dùng delegate muốn thực thi 1 lúc nhiều function hay dùng 1 function để làm tham số cho 1 function khác.

- Predicate ( Predicate<T in> ): Predicate là 1 delegate được tích hợp sẵn ( build-in ) trong C# với kiểu trả về là bool. Predicate chỉ có thể nhận vào 1 params duy nhất.

- Action ( Action<T in1, T in2, ...> ): Action là 1 delegate được tích hợp sẵn ( build-in ) trong C# với kiểu trả về là void. Với in1, int2 là tham số nhận vào.

- Func ( Func<T1, T2, T3, ... Tn> ): Func là 1 delegate được tích hợp sẵn ( build-in ) trong C# với kiểu trả về nằm ở cuối cùng.

--- Lambda trong C#

- Lambda trong C# giống như 1 anonymous function, tương tự như arrow function trong js.

- Hàm Lambda dùng để thực thi 1 logic đơn giản mà không cần tạo ra 1 hàm riêng biệt. Hàm lambda sử dụng khi muốn truyền một hàm nhỏ và có thể không cần sử dụng lại hàm đó.

- Lambda có thể làm việc với delegate, event handling, async/await, functional programming.

--- Build in method Select(), Where() trong C#

- Select() = map(), Where() = filter()

--- Event trong C#

- Publisher: class phát sự kiện.

- Subcriber: class nhận sự kiện.

- event trong C# là 1 cơ chế thông báo cho các class khác rằng 1 hành động đã xảy ra.

- 1 biến event có thể được xem như 1 mutilcast delegate. event phải được khai báo như 1 field, không phải 1 thuộc tính.

- event dựa trên delegate model, trong khi delegate model dựa trên Observer Design Pattern.

- EventHandler là một kiểu delegate được tích hợp sẵn trong .NET chuyên sử dụng để khai báo và tạo ra các sự kiện ( events ).

- EventHandler ~ delegate void Name(object? sender, EventArgs arg).

--- Extension Method ( phương thức mở rộng ) trong C#

- Phương thức mở rộng là các phương thức được thêm vào lớp, cấu trúc, interface có sẵn mà không cần thiết phải thay đổi code của lớp đó. Các phương thức mở rộng là static.

- Sử dụng phương thức mở rộng khi muốn tạo ra 1 phương thức tĩnh mà không cần phải tạo 1 lớp con hay thay đổi lớp gốc.

- Để chỉ một phương thức thành 1 phương thức mở rộng, ta sử dụng keyword this ở trước tham số đầu tiên. This này là đối tượng bạn muốn mở rộng.

--- Overloading Operator ( quá tải toán tử ) trong C#

- Là kỹ thuật giúp define ra các toán tử mới trên những đối tượng do bạn định nghĩa.

--- Indexer trong C#

- Indexer là kỹ thuật giúp chúng ta truy cập vào các trường dữ liệu của 1 lớp thông qua [chỉ mục] do chúng ta tự định nghĩa.

--- Multithreading trong C#

- Multithreading là 1 kỹ thuật để cùng 1 lúc có thể xử lý nhiều tác vụ. Mặc định C# có 2 luồng: main thread và thread UI.

--- Async/Await trong C#

- Lập trình bất đồng bộ ( asynchronous ) là tạo ra các app có thể chạy đa luồng ( multithreading )

- Lớp Task<T> biểu thị cho tác vụ bất đồng bộ, từ đó chạy được code bất đồng bộ.

--- Reflection trong C#

- Là kỹ thuật lấy thông tin của 1 object bằng thông tin kiểu dữ liệu ( GetType ) ở thời điểm thực thi ( runtime ).

- Lớp Type là lớp cung cấp 1 số methods để lấy thông tin của 1 đối tượng: GetMethod(), GetFields(), GetProperties(), ... trong thời gian chạy ( runtime ).

--- Attribute/Annotation trong C#

- Attribute là 1 thẻ khai báo. Attribute cho phép gán metadata ( siêu dữ liệu ) vào lớp, phương thức hoặc thuộc tính những đoạn code mở rộng.

- metadata: loại data cung cấp các thông tin vê đối tượng như tên, type, desc, quyền truy cập, các ràng buộc , ...

- 1 số Attribute được build-in trong .NET, [required()], [StringLength()], [DataType()], ...

--- using trong C#

- using được sử dụng để tạo một phạm vi có giới hạn cho một đối tượng và đảm bảo rằng đối tượng sẽ được giải phóng ngay sau khi phạm vi đó kết thúc.

--- Task trong c#

- Task là một loại dữ liệu đại diện cho một tác vụ (hoặc một công việc) được thực thi bất đồng bộ. Task cung cấp một cơ chế để theo dõi tiến trình và kết quả của tác vụ.

- Khi bạn sử dụng async, phương thức của bạn thường sẽ trả về một đối tượng Task để biểu diễn kết quả của tác vụ đó. Task có thể trả về một giá trị (ví dụ: Task<string>) hoặc không trả về giá trị (ví dụ: Task).

- Task cung cấp các phương thức và thuộc tính để theo dõi trạng thái của tác vụ, như IsCompleted, IsFaulted, Result,...

--- HttpClientHandler, DelegatingHandler cho HttpClient

- DelegatingHandler: là 1 handler đặc biệt, nó như 1 Middleware để tạo ra một pipeline ( chuỗi các handler ).

--- Stream trong C#

- Stream đại diện cho 1 luồng dữ liệu, tức là 1 chuỗi liên tục các byte đang được truyền hoặc xử lý.

- Trong C# thì stream là 1 lớp trừu tượng, được sử dụng để làm việc các với luồng dữ liệu, cho phép đọc và ghi dữ liệu từ các nguồn khác như folder, memory và mạng ( FileStream,... )

- Có 2 loại stream: Input và Output.

- Stream là tài nguyên có hạn nên cần Close() khi ko cần use nữa.

--- ADO.NET trong C#

- ADO ( ActiveX Data Object ) là tập hợp các thư viện cho phép application tương tác ( CRUD ) với database.

- Kiến trúc của ADO gồm 2 phần: DataProvider và DataSet

DataProvider: Là tập hợp các class và Interface để connect và tương tác với database. Mỗi loại data thì có 1 DataProvider riêng ( ví dụ: DataProvider default trong .NET Core là SqlClient connect đến SqlServer ).

DataSet:
