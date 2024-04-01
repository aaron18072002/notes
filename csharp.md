--- Field và Property

- Field: là biến được khai báo trong class. Nếu không khởi tạo giá trị cho Field, nó sẽ tự động set default value của type của Field cho Field đó - việc này gọi là backing field.

- Một số default value cho từng type: int - 0, object - null, ...

- Name của Public Field nên start với uppercase, còn Private Field thì start với \_. VD: ( public int Num, private int \_num ).

- Property: là 1 cặp phương thức đặc biệt dùng dể truy cập và sửa đổi giá trị của field. VD: { get; set; }

- Field không thể bị override, nhưng Property thì có thể bị override.

- Methods đại diện cho ( represent ) cho action trong khi Properties đại diện cho data.

- Computed Property là một Property chỉ có phương thức Get;

--- Constructor trong C#

- Một method dùng để khởi tạo ( instantiate ) có cùng tên với class cha của nó.

- Có nghiệm vụ khởi tạo giá trị cho các thuộc tính trong class hoặc nhận giá trị đầu vào và gán các trị đó vào các thuộc tính.

--- Top-level statement

- Các Top-level statement code khi compile sẽ auto được thêm vào class Program và static void Main(). Và chỉ có 1 file là được viết Top-level statement.

--- Methods trong class

- Name của methods nên bắt đầu bằng verb.

--- Có 3 kiểu dữ liệu trong C#

- Values Types ( Kiểu giá trị ): Là kiểu giá trị mà được lưu trữ dưới dạng value trong bộ nhớ. Có nghĩa là biến đó lưu trữ trực tiếp giá trị được gán ( Bool, byte, char, decimal, double, Enum, float, int, long, short and struct ).

- Reference Types ( Kiểu tham chiếu ): Không giống như kiểu giá trị, kiểu tham chiếu không lưu trữ trực tiếp giá trị của nó. Thay vào đó, nó lưu trữ địa chỉ nơi mà giá trị được giữ trong bộ nhớ. Giống như nó đang lưu trữ một con trỏ trỏ đến địa chỉ nơi biến được lưu trữ ( String, arrays, collections , classes, interface and delegate ).

--> Trong đó, Array là một tập hợp các giá trị có cùng kiểu dữ liệu được lưu trữ tại các vị trí liền kề nhau trong bộ nhớ.

- Pointer Types ( Kiểu con trỏ ): Nhằm mục đích lưu trữ địa chỉ của 1 con trỏ khác.

--- Struct trong C#

- Struct khác với Class như thế nào: Tất cả struct là sealed, nghĩa là nó không thể được kế thừa, vì thế không thể chứa abstract và virtual. Struct không có Finalizer method.

- Có thể biến 1 struct trở thành immutable với keyword readonly, sau đó tất cả field và properties cửa struct đó cũng phải là expilicit readonly hoặc init. VÍ DỤ: readonly struct Point { private readony int z; public int X { get; init; } }

- Một struct thường không nên chứa field hoặc properties kiểu referrence type. Nguyên nhân chính là bởi vì cách các đối tượng kiểu cấu trúc được xử lý và sao chép. Khi một đối tượng kiểu cấu trúc được sao chép, toàn bộ nội dung của nó sẽ được sao chép sang một bản sao mới, bao gồm cả các trường và thuộc tính. Nếu một struct chứa một trường hoặc thuộc tính của kiểu tham chiếu, việc sao chép đối tượng sẽ chỉ sao chép tham chiếu đến đối tượng gốc, không phải là sao chép toàn bộ đối tượng đó.

--- Có 4 loại toán tử trong C#

- Toán tử số học: ( + - nhân / % ++ -- )
- Toán tử gán: ( = += -= nhân= /= %= &= )
- Toán tử so sánh: ( == != >= <= > < )
- Toán tử logic: ( && || ! )

--- Parsing trong C#

- Là tiến trình ( process ) chuyển đổi ( transform ) data type.

--- Errors trong C#

- Runtime errors: Xảy ra khi application đang run.

- Compilation errors: Xảy ra trong quá trình biên dịch. Prevent app của chúng ta khỏi việc compiled and run.

- Logical errros: App không bị crash nhưng nó không work đúng cách.

--- Exception trong c#

- Exception là cách mà C# trình bày ( represent ) các runtime errors

- Tất cả Exception trong C# đều devired from System.Exception base class.

- Chỉ nên dùng try catch chỉ khi chúng ta thật sự thấy được là code có thể cause an error, có thể dùng multiple catch với multiple exceptions khác nhau. Logic trong finally luôn chạy dù try hay catch được gọi. Và finally thường dùng để clean một resources bị leak. VÍ DỤ: Dùng để ngắt connect tới db sau khi try hoặc catch đã dùng xong.

- Dùng quá nhiều exceptions có thể reduce performance. Exception chỉ nên được dùng cho những trường hợp cần sử dụng nó, chứ không phải control flow của program.

- Xài if else statements thay vì mutiple catch exceptions cũng có thể tăng performance.

- Một type exception hay dùng: NullReferenceException, FormatException, DivideByZeroException, ArgumentException, ArgumentNullException, ArgumentOutOfRangeException, IndexOutOfRangeException, InvalidOperatorException, NotImplmentedException, HttpRequestException, InvalidCastException, KeyNotFoundException.

- StackOverflowException: Thường xảy ra khi dùng hàm đệ quy mà điều kiện dừng sai dẫn đến infinity loop.

- OutOfMemoryException: Xảy ra khi memory leaks hoặc quá nhiều memory cần được sử dụng so với sức chứa ( capabilities ) của app.

- Nên cố gằng throw ra specific exception nhất có thể vì nếu throw base Exception. Sẽ không thể phân biệt ( distingish ) đó chính xác là kiểu exception nào. Và có thể base Exception sẽ catch nhầm một exception nào đó. Nếu specific exception không thể mô tả chi tiết error hơn global exception thì ta nên catch nó ở global exception luôn.

- Ở locally - specific exception (lowest level): không nên log error mà nên handle nó meaning hơn.

- Một custom exception nên có chữ cuối là Exception và devired base Exception class.

--- Throw ex và throw

- throw ex: Exception sẽ được tạo mới và ném đi. Stack Trace sẽ start từ vị trí ( place ) nơi Exception được ném. Điều này có nghĩa những method calls trước đó bị mất. Nghĩa là throw ex không bảo toàn ( does not preserves ) Stack Trace.

- throw : Stack Trace sẽ start từ place nơi mà Exception được khởi tạo, không phải place mà Exception throw. Điều này bảo toàn ( Preserves ) những thông tin và các method calls trước đó.

--- Stack Trace trong Exception

- Stack Trace là một thuộc tính của Exception.

- Stack Trace là 1 call stack chứa tất cả những methods mà đã được gọi trước thời điểm mà Exception được thrown ra.

--- InnerException trong Exception

- InnerException là 1 thuộc tính của Exception. Dùng để lưu trữ Exception gốc mà đã tạo ra Exception hiện tại.

--- Global Try Catch block

- Dùng để catch bất cứ Exception nào chưa được handle ở bất cứ đâu.

- Nó bao quanh ( surround ) entry point. Entry point là nơi mà first method được gọi. Trong method đó có thể gọi nhiều methods khác nữa. Trong console app, Main method nằm trong class Program.

--- Solution, Project khi trong Visual Studio

- Solution là 1 collection các Projects

--- String Interpolation và String Concatenation trong C#

- String Interpolation: $"{variable}".

- String Concatenation: " " + variable + " ".

--- Expresstion và Statement trong C#

- 1 expresstion là 1 đoạn code ( a piece of code ) mà tạo ra ( produces - evaluates ) a value.

- statement là a piece of code that does not evaluates a value. VD ( if else statement ).

--- Expression-bodied methods: 1 cách viết function shorter trong C# giống với arrow function trong js.

--- Break và Continue trong C#

- Break: Dừng việc thực thi ( execution ) của toàn bộ vòng lặp

- Continue: Break lần lặp ( iteration ) hiện tại và đi thẳng đến lần lặp tiếp theo.

--- Multi dimensional Array ( mảng đa chiều ) trong C#

- VÍ DỤ: new nums[i,j] ( i là chiều ngang - horizen, j là chiều dọc - vertical )

--- Khái niệm Repositories trong C#

- Repositories là khái niệm dùng để nói về class or component mà nó đóng gói ( encapsulate ) logic cần thiết để ( required to ) access data sources.

--- Enum type trong C#

- Enum ( stands for enumeration ): là 1 data type được sử dụng để định nghĩa một tập hợp các hằng số được định danh bằng tên ( a set of named constants ). Mỗi hằng số trong enum có một số nguyên tương ứng.

- Enum là kiểu tham trị.

--- Casting trong C#

- Casting là một quá trình ( process ) chuyển đổi một variable từ type này sang type khác.

- Có 2 kiểu casting: Implicit Casting và Explicit Casting.

- Cast là performance-heavy operator.

--- Base keyword trong C#

- Base dùng để refer to base class constructor, và tất cả những method ở base class mà class con ( derived class ) có thể truy cập được.

--- Mảng thuộc IEnumrable interface trong C# có các thuộc tính sau

- Là 1 mảng read-only, không thể thêm hay bớt elements.

- Chỉ duyệt theo 1 chiều, từ đầu đến cuối.

- IEnumrable có thể đại diện cho mọi Collection bao gồm cả Array.

- ICollection interface và IList interface trong .NET

- IEnumarable -> ICollection -> IList. Với IEumarable là base class của ICollection và ICollection và base class của IList.

- IList bổ sung các method như IndexOf(item), Insert(int index, T item), RemoveAt(int index) và kỹ thuật indexer theo index.

--- Type class trong C#

- Type là class represent cho types. Nó chứa các properties như type's name, namespace mà nó thuộc về ( belong to ), the base type, hoặc là 1 list các type's constructors. Nó là một phần của cơ chế reflection ( reflection mechnism ).

--- GetType() và typeof() trong C#

- Cả 2 đều return Type data.

- typeof để lấy info về data type tại thời điểm compile, còn GetType() thì được dùng để lấy info và data type của một instance tại thời điểm run-time.

--- Keyword where trong C#

- where dùng để thiết lập các ràng buộc về type ( type constrains ) cho các type parameters trong generic. VÍ DỤ: public class MyClass<T> where T : class - nghĩa là tham số kiểu T phải là một tham số kiểu class.

- 1 type parameter có thể có nhiều type constrains và được ngăn cách bởi dấu phẩy. VÍ DỤ: public T GetPetName<T>(T pet) where T : Pet, IComparable<T>

- Chúng ta cũng có thể gán type constrains cho nhiều type parameters. VÍ DỤ: public void PrintPetAndOwnerName<TPet, TOwner>(TPet pet, TOwner owner) where TPet : Pet, IComparable<Tpet> where IOwner : new()

- 1 số type constrains thường dùng: https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters

--- IComparable<T> Interface trong C#

- IComparable là một interface cung cấp cách để 2 object so sánh với nhau cho mục đích sorting.

- Class implement IComparable cung cấp một phương thức CompareTo(obj) để so sánh nó với một đối tượng khác. Phương thức này trả về negative number nếu đối tượng hiện tại nhỏ hơn đối tượng được so sánh, trả về 0 nếu chúng bằng nhau, và trả về positive number nếu đối tượng hiện tại lớn hơn đối tượng được so sánh. Trả về negative number chứng tỏ current object sẽ đứng trước object trong tham số, và ngược lại.

- Ta thường dùng IComparable để so sánh 2 object với cùng data type.

--- IEquatable Interface trong C#

- Mục đích: Được sử dụng để xác định cách so sánh giữa hai đối tượng của cùng một kiểu dữ liệu.

- Phương thức: Interface này chỉ định một phương thức Equals(object) mà mọi lớp triển khai phải thực hiện. Phương thức này cho phép so sánh một đối tượng với một đối tượng khác cùng kiểu và trả về kết quả là true nếu chúng bằng nhau và false nếu không.

- Sử dụng: Thích hợp khi bạn cần kiểm tra tính bằng nhau của hai đối tượng cùng kiểu, chẳng hạn khi so sánh hai đối tượng dựa trên nội dung của chúng. Và khi bạn không muốn sử dụng method Equal() mặc định của System.Object vì method này sử dụng các mechanism như boxing, unboxing và reflection gây ảnh hưởng tiêu cực tới performance.

--- LINQ trong C#

- LINQ ( Language Integrated Query ) là 1 thư viện chứa nhiều methods giúp chúng ta query nhiều loại data một 1 cách simple và hiệu quả ( efficient ) hơn. Cụ thể, LINQ cung cấp một cú pháp để query, filter, group, và transform dữ liệu từ các nguồn dữ liệu khác nhau như List, Array, databases, XML, và các collections khác.

- Hầu hết các methods trong LINQ đều là extension method cho các biến thuộc IEnumrable<T> type. Và LINQ methods sẽ không modify collection gốc mà thay vào đó sẽ tạo ra 1 collection mới.

- Deferred Execution ( hoãn thực thi ) nghĩa là việc tính toán của 1 LINQ expression bị delay cho đến khi result được dùng đến. Nó giúp chúng ta luôn làm việc với data mới nhất và giúp cải thiện performce bằng việc tránh các logic chưa cần dùng đến. VÍ DỤ: Khi sử dụng các methods như "Where", "Select", "OrderBy",... thì các methods đó không thực thi ngay lập tức mà thay vào đó nó tạo ra 1 query, chỉ khi mà chúng ta yêu cầu result bằng cách lặp qua result đó hoặc sử dụng một method mà thay đổi result như "ToList()", "ToArray()" thì LINQ expression mới thực thi.

- 1 số LINQ methods thường dùng: All(), Any(), Count() - return int, LongCount() - return long, Contains(), OrderBy() - mặc định là ascending, OrderByDescending(), Last(), First(), LastOrDefault(), FirstOrDefault(), Select() = map(), Where() = filter() trong JS

--- Hash Functions trong .NET

- GetHashCode() là 1 hash function được triển khai cho C# object ( cả value type và reference type ).

- Đối với các kiểu giá trị như int, double, struct, enum,... GetHashCode() thường sẽ tính hash code dựa trên giá trị của chính nó. Ví dụ, hash code của một số nguyên sẽ bằng giá trị của số nguyên đó. Vì thế có thể sẽ dẫn đến key của 2 value type bằng nhau nếu chúng có value như nhau.

- Đối với các kiểu tham chiếu, GetHashCode() thường sẽ sử dụng địa chỉ của đối tượng để tính hash code. Mặc định, phương thức GetHashCode() sẽ trả về giá trị hash code dựa trên địa chỉ bộ nhớ của đối tượng. Điều này đồng nghĩa với việc hai đối tượng tham chiếu khác nhau sẽ có hai mã hash code khác nhau, ngay cả khi chúng tham chiếu đến cùng một nội dung.

- Trong .NET, các hàm băm (hash function) thường được sử dụng để ánh xạ dữ liệu từ các loại dữ liệu khác nhau sang các giá trị hash code duy nhất. Cụ thể, .NET Framework cung cấp một số lớp để thực hiện các chức năng băm, chẳng hạn như MD5, SHA1, SHA256, SHA384, và SHA512.

- Hash code đóng vai trò như key trong hashed collection. Các loại hashed collections phổ biến: Dictionary, HashSet, ...

- Nếu chúng override lại implemention của Equal() thì ta cũng nên override lại GetHashCode(). VÍ DỤ: Nếu chúng ta ghi đè lại Equal() để so sánh theo ID của object thì ta cũng nên ghi đè lại GetHashCode() để hash theo ID cho nó đồng bộ.

- Nếu 1 object được sử dụng để làm key của 1 Dictionary, nó nên là immutable object, hoặc ít nhất các thuộc tính của nó phải là immutable.

--- Có 4 kiểu class trong C#

- static class: 1 Class được xác định là static là class tĩnh, không thể tạo các object từ class đó, khi khai báo 1 static class thì yêu cầu tất cả các thuộc tính lẫn methods trong class đó cũng phải static. Static Class dùng để lưu các thông tin dùng chung cho toàn bộ app của chúng ta. Một static class không được nested trong 1 class khác.

- partial class: partial class được xem như các lớp con của 1 lớp cha nào đó nằm ở nhiều file (.cs) khác nhau. Nhiều file này kết hợp thành 1 trong compile-time. Các partial class muốn liên kết thì phải có cùng tên và namespace. Giống như việc chia nhỏ 1 class cha thành nhiều class con và phân bổ chúng ở nhiều file (.cs) khác nhau.

- abstract class: Abstract có nghĩa là "dở dang, chưa hoàn thiện" -> không thể tạo các instances từ Abstract Class ( Abstract class cannot be instantiate ). Abstract class cung cấp những cơ sở để những class con có thể kế thừa và override lại các method sẵn có .Nếu trong app của chúng ta có quá nhiều Class giống nhau về thuộc tính hay method nào đó thì ta có thể tạo ra 1 Abstract Class cung cấp Abstract method để cho các Class kia có thể kế thừa và ghi đè lại Abstract Method đó để giải quyết vấn đề. ( Abstract methods tên là TinhDienTich thuộc Abstract Shape - Các Class con kế thừa Class Shape có thể override lại phương thức TinhDienTich để tính toán ).

- sealed class: Lớp này không thể được kế thừa.

--- Từ khóa Static

- Static Class: 1 Class được xác định là static là class tĩnh ( implicit static ) và implicut sealed, không thể tạo các object và thừa kế từ class đó, khi khai báo 1 static class thì yêu cầu tất cả các thuộc tính lẫn methods trong class đó cũng phải static. Static Class dùng để lưu các thông tin dùng chung cho toàn bộ app của chúng ta.

- Static cho thuộc tính ( properties ) và phương thức ( methods ): Hàm và biến static không thuộc về object ( not belong to specified instance ) mà thuộc về Class, không thể overrdie 1 static method ,chúng có thể được truy cập trực tiếp từ Class mà không cần tạo ra các instances. Static Properties sẽ trả về kết quả giống nhau cho mọi object được tạo ra tử class cha. Không thể dùng một non-static method bên trong 1 static method.

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

- Cả List và ArrayList đều add item vào cuối danh sách khi dùng method Add().

- UNDER THE HOOD: Khi một element mới được thêm vào, một List mới sẽ được tạo ra và sức chứa của nó sẽ lớn hơn List cũ rồi List cũ sẽ gán toàn bộ element của nó qua List mới, sau đó List cũ sẽ được thay thế bởi List mới, cuối cùng thì element mới được thêm vào cuối List đó.

--> Dictionary

- Dictionary là 1 generic collection. Là 1 collection với các cặp key-value làm phần tử. Mỗi phần tử của Dictionary có type là KeyValuePair<T1, T2> .

- Lớp Dictionary<Tkey,TValue> khá giống SortedList, Dictionary được thiết kế với mục đích tăng hiệu quả với tập dữ liệu lớn, phức tạp.

- Có thể truy cập đến các phần tử Dictionary thông qua key lẫn index. Không cho phép trùng key

--> HashSet

- HashSet là tập hợp các phần tử không cùng giá trị.

- Dùng để giải quyết các bài toán liên quan tới phép giao, phép hợp.

--> Tuple

- Tuple là 1 generic collection, nó có thể lưu trữ ( stored ) một tập hợp các phần từ ( a set of elements ) với nhiều kiểu dữ liệu khác nhau ( mutiple diferent data types ).

- Tuple chỉ chứa max được 8 phần tử.

--- ValueTuple trong C#

- ValueTuple là value type trong khi Tuple là reference type. ValueTuple là mutable trong khi Tuple là immutable.

--- Record và Positional Record và Record Structs trong C#

- Record: là một cấu trúc dữ liệu có thể immutable, được xác định bằng cách sử dụng từ khóa record, nghĩa là nó được truyền theo giá trị và không thể thay đổi sau khi tạo. Record là một kiểu dữ liệu tham chiếu, nhưng nó support việc so sánh theo giá trị. Khác với struct, records hỗ trợ việc inheritance. Record thường dùng để DTO từ json file.

- Record Structs: Thuộc kiểu dữ liệu tham trị. Record Structs mặc định là mutable. Record Structs đã auto override ToString() để trả về toàn bộ fields của nó.

- Positional record: Là một loại record trong C# có cú pháp ngắn gọn cho việc định nghĩa các thuộc tính của nó ( không có constructor ). Trong một positional record, các thuộc tính được xác định theo thứ tự vị trí của chúng trong khai báo record, và không cần phải xác định tên cho từng thuộc tính. Positional Record mặc định là mutable.

--- Generic trong C#

- Generic trong C# là một tính năng trong C#. Trong đó kiểu dữ liệu ( của biến, tham số, kiểu trả về của các methods, class ) được xác định ở giai tạo khởi tạo.

- Generic allow to define generic classes, interface, abstract classes, fields, methods, events, delegates using Type Parameter without specific data type. A type parameter is a placeholder for paritucal type specified ( type được chỉ định cụ thể ) when create an instance of the generic type.

- C# complier chỉ có thể dùng typeo of arguments để suy ra ( infer ) generic type, không thể dùng type của reuslt được.

--- Anonymous Type ( Kiểu vô danh )

- Được khai báo bằng từ khóa new { }.

- Read-only, không thể modify các biến trong kiểu vô danh.

- Chỉ chứa được fields và methods, không chứa được methods.

--- Sự khác biệt giữa late binding và early binding trong C#

- Late binding và early binding là ví dụ về tính đa hình trong OOP

- Early binding: xảy ra tại thời điểm biên dịch. Nó kiểm tra các methods và thuộc tính của static class.

VÍ DỤ: khi gọi 1 method từ 1 object, early binding sẽ kiểm tra rằng method đó tồn tại và có thể được gọi từ đối tượng đó hay không.

- Late binding: xảy ra tại thời điểm runtime. Late binding xảy ra khi đối tượng là 1 dynamic type. Biến kiểu động - ngầm định - khai báo với từ khóa dynamic, type của biến dynamic type được xác định tại thời điểm runtime ( khác với var - type được xác định tại thời điểm biên dịch ).

--- Mutex trong C#

- Trong multithreading, Mutex là 1 cơ chế đồng bộ hóa được sử dụng để đảm bảo rằng chỉ có 1 luồng ( thread ) có thể truy cập vào 1 tài nguyên cụ thể tại 1 thời điểm cụ thể. Mutex được sử dụng để tránh conflict thread và đảm bảo dữ liệu được truy cập 1 cách an toàn.

--- Overloading và Override

Cả 2 đều là những kỹ thuật giúp tạo nên tính đa hình ( Polymorphism )

Overloading - Nạp chồng: Kỹ thuật tạo ra các methods có cùng tên nhưng giá trị trả về và logic trong đó có thể khác nhau tại các ngữ cảnh khác nhau. Chỉ có method main() là không được nạp chồng.

Để implement overloading trong C#:

- Thay đổi số lượng tham số ( count of parameters ).

- Thay đổi thứ tự tham số ( order of parameters ).

- Sử dụng type khác nhau cho tham số

Override: Ghi đè lại method ở class cha mà class con kế thừa

--- Namespace trong C#

- Namespace là một keyword được dùng để khai báo ( declare ) 1 phạm vi chứa một tập hợp ( a set ) các relatived types.

--- Implicit Conversion và Explicit trong C#

- Implicit Conversion - Chuyển đổi ngầm trong C# sẽ được auto implment khi mà chúng ta convert 1 data type sang 1 data type lớn hơn.

- Một số implicit conversion gọi là upcasting: Xảy ra khi convert một devired class thành một base class. VÍ DỤ: Ingredient cherry = new Cherry();

- Downcasting - explicit cast expression ngược lại với upcasting, nó require an explicit cast. VÍ DỤ: Animal cat = (Cat)new Animal();

- Khi convert thất bại, cast expression sẽ throw InvalidCastException. Còn với as, nó sẽ return null. VÍ DỤ: Cat cat = animal as Cat;

--- Toán tử is trong C#

- Dùng để check type của một object và trả về boolean. VÍ DỤ: bool isString = word is string;

--- String và StringBuilder trong C#

- Về mặt cấu trúc giải thuật, String là array chứa các characters, mà length của array là fixed. Do đó, String là đối tượng immutable. Nghĩa là mỗi lần thao tác với 1 String, C# sẽ tự động tạo ra 1 String mới trong memory hay nói cách khác là tạo một array of characters mới. String cũng support Equals() và GetHashCode() method.

- String tối ưu hơn Char[] ở cơ chế string interning: String Interning trong C# là một quá trình tối ưu hóa bộ nhớ mà C# thực hiện để giảm bớt việc lặp lại cấp phát bộ nhớ cho các chuỗi có cùng giá trị. Khi bạn tạo một chuỗi mới, .NET Framework đầu tiên kiểm tra xem chuỗi đó đã được interned (được tham chiếu đến một vùng bộ nhớ duy nhất) chưa. Nếu chuỗi đã được interned trước đó, thì tham chiếu đến vùng bộ nhớ đó sẽ được trả về. Nếu không, chuỗi mới sẽ được thêm vào pool intern và được tham chiếu đến vùng bộ nhớ mới. String Interning sẽ không hoạt động nếu ta set string là 1 mutable. String Interning sử dụng Flyweight Design Pattern.

- StringBuilder allow bạn change 1 chuỗi trực tiếp trong memory thay vì tạo 1 bản copy mới. Default size của 1 StringBuilder là 16 nhưng nó có thể update 1 cách tự động. 1 StringBuilder object hỗ trợ các method như AppendLine, Clear, Replace, ...

--- Sự khác biệt giữa cách truyền tham số ref và out

- Cả 2 đều được dùng để truyền tham chiếu tới hàm.

- Biến truyền vào với keyword out không cần phải khởi tạo giá trị ban đầu. Vậy nên biến out chỉ dùng để xuất giá trị ra thôi.

- Dùng out khi muốn vượt qua ( bypass ) giới hạn của 1 function là chỉ trả về 1 result.

- Về mặt kỹ thuật, khi bạn truyền một biến bằng ref, một con trỏ ( pointer ) đến vùng nhớ của biến đó được truyền vào phương thức. Với out cũng truyền con trỏ đến vùng nhớ của biến, nhưng với điều kiện rằng phương thức phải gán giá trị cho biến đó trước khi kết thúc.

- VẤN ĐỀ: Chúng ta muốn truyền 1 tham trị với tư cách là tham số vào 1 function và ta muốn biến tham trị đó modify bởi logic trong function.

--- So sánh toán tử == và equals()

- Cả 2 đều trả về true, false.

- Toán tử == sẽ so sánh điểm tham chiếu của biến được so sánh.

- Phương thức equals() dùng để so sánh giá trị được mang bởi các đối tượng.

--- Từ khóa this

- This dùng để tham chiếu ( references ) - ánh xạ đến đối tượng hiện tại ( current object ).

- Hoặc dùng để refer to another constructor trong cùng 1 class. VD: public Animal(string name, string sound) : this(name) - this(name) ám chỉ việc gọi 1 constructor khác cùng class nơi mà chỉ nhận 1 tham số là name.

--- Default Value trong C#

- Có thể set Default Value với các parameters trong function và parameter with default value phải nằm cuối order of parameters . VÍ DỤ: public int Reshedule(string patientName, int daysFromNow = 7).

- Default Value phải là ( must be ) a compile-time constant.

--- Struct trong C#

- Struct như 1 custom type do chúng ta tự định nghĩa với fields và methods giống như 1 class.

- Struct là 1 value type, nó lưu trữ giá trị trực tiếp của nó trong memory.

- Struct khác với class là nó không thể được kế thừa.

--- So sánh Const và ReadOnly trong C#

- Cả biến const và ciến readonly đều không thể bị modified.

- Const là 1 compile-time constant cũng như là 1 implicitly static. Biến const bắt buộc phải được gán giá trị lúc khai báo và không thể modify. Type của const được xác định ở thời điểm biên dịch.

- ReadOnly là 1 runtime constant. Biến ReadOnly có thể được gán giá trị lúc khai báo hoặc trong constructor. Type của readOnly được xác định ở thời điểm khởi tạo.

- Const áp dụng với basic type, string và 1 số type mà không thể modify tại thời điểm biên dịch.

- ReadOnly áp dụng được cho tham chiếu lẫn tham trị trừ Delegate và event.

--- Init expression trong C#

- Từ khóa init được sử dụng để chỉ định một thuộc tính (property) chỉ có thể được gán giá trị một lần duy nhất trong quá trình khởi tạo, sau đó không thể thay đổi giá trị của nó. Nó tương tự như việc sử dụng set trong một thuộc tính chỉ đọc (read-only property), nhưng khác biệt chính là bạn có thể gán giá trị trong quá trình khởi tạo, sau đó không thể thay đổi nó ở bất kỳ thời điểm nào sau đó.

- VÍ DỤ: public string Title { get; init; }, init ở đây có nghĩa Title vẫn có thể bị gán trong phạm vi cửa class hoặc trong constructor. Và nó cũng ám chỉ Title là implicit readonly.

--- With expression trong C#

- Từ khóa with dùng để để tạo ra một bản sao của một đối tượng đã tồn tại với một số thay đổi được áp dụng. Điều này giúp tránh việc phải tạo ra một bản sao hoàn toàn mới của đối tượng và sao chép lại các giá trị không thay đổi.

- VÍ DỤ: Person person = new Person { Name = "John", Age = 30 }; Person newPerson = originalPerson with { Age = 40 };

--- Từ khóa null

- null là từ khóa ám chỉ rằng nó không tham chiếu tới đối tượng nào cả.

- Nếu 1 reference type variable tham chiếu tới null, nghĩa là nó không tham chiếu tới object nào cả.

--- Delegate trong C#

- Delegate trong C# là một kiểu dữ liệu đặc biệt để khai báo ( define ) biến tham chiếu trỏ tới địa chỉ các hàm hoặc methods. Với điều kiện là các hàm và methods đó có cùng kiểu dữ liệu trả và cùng kiểu dữ liệu tham số đầu vào.

- Một biến delegate có thể tham chiếu ( reference ) tới nhiều functions gọi là mutilcast và một function có thể được gọi nhiều lần trong cùng 1 biến delegate. Những functions đó được implment 1 cách tuần tự.

- Dùng delegate muốn thực thi 1 lúc nhiều function hay dùng 1 function để làm tham số cho 1 function khác và gọi lại function đó bên trong để thực hiện logic.

- Predicate ( Predicate<T in> ): Predicate là 1 delegate được tích hợp sẵn ( build-in ) trong C# với kiểu trả về là bool. Predicate chỉ có thể nhận vào 1 params duy nhất.

- Action ( Action<T in1, T in2, ...> ): Action là 1 delegate được tích hợp sẵn ( build-in ) trong C# với kiểu trả về là void.

- Func ( Func<T1, T2, T3, ... Tn> ): Func là 1 delegate được tích hợp sẵn ( build-in ) trong C# với kiểu trả về là type parameter cuối cùng.

--- Lambda trong C#

- Lambda trong C# giống như 1 anonymous function, tương tự như arrow function trong js.

- Hàm Lambda dùng để thực thi 1 logic đơn giản mà không cần tạo ra 1 hàm riêng biệt. Hàm lambda sử dụng khi muốn truyền một hàm nhỏ và có thể không cần sử dụng lại hàm đó.

- Lambda có thể làm việc với event handling, async/await, functional programming và đặc biệt là với delegate và LINQ library.

--- Extension Method ( phương thức mở rộng ) trong C#

- Phương thức mở rộng là các phương thức được thêm vào lớp, interface có sẵn mà không cần thiết phải thay đổi code của lớp đó. Class mà chứa extension methods phải là static và bản thân extension methods đó cũng phải là static.

- Sử dụng phương thức mở rộng khi muốn tạo ra 1 phương thức tĩnh mà không cần phải tạo 1 lớp con hay thay đổi lớp gốc.

- Để chỉ một phương thức thành 1 phương thức mở rộng, ta sử dụng keyword this ở trước tham số đầu tiên. This này reference tới đối tượng bạn dùng phương thức mở rộng cho.

--- Overloading Operator trong C#

- Là kỹ thuật giúp define ra các toán tử mới trên những đối tượng do bạn định nghĩa ( defined bên trong class ).

- Có kiểu Overloading Operator là implicit và explicit.

- Các Overloading Operator bắt buộc phải là static method. VÍ DỤ: public static bool operator ==(Point p1, Point p2) { return p1.Equals(p2); }

--- Pure Function trong C#

- Là những Functions chỉ xử lý tham số mà nó được truyền vào chứ không có side effect ( ảnh hưởng tới các biến, hàm, class bên ngoài ).

--- Indexer trong C#

- Indexer là kỹ thuật giúp chúng ta truy cập vào các trường dữ liệu của 1 lớp thông qua [chỉ mục] do chúng ta tự định nghĩa.

- Indexer provide a way to access elements of a collection or class by using square bracket notation ( dấu ngoặc vuông - [] ).

- Thread trong C#

-- Thread là các đơn vị ( units ) mà control flow của program.

--- Multithreading trong C#

- Multithreading là 1 kỹ thuật để cùng 1 lúc có thể xử lý nhiều tác vụ. Mặc định C# có 2 luồng: main thread và thread UI.

--- Async/Await trong C#

- Lập trình bất đồng bộ ( asynchronous ) là tạo ra các app có thể chạy đa luồng ( multithreading )

- Lớp Task<T> biểu thị cho tác vụ bất đồng bộ, từ đó chạy được code bất đồng bộ.

--- Reflection trong C#

- Reflection là cơ chế cho phép bạn xem và tương tác với cấu trúc của các loại (types) trong thời gian chạy của ứng dụng.

- Là kỹ thuật lấy thông tin của 1 object thông qua kiểu dữ liệu ( GetType ) ở thời điểm thực thi ( runtime ). Method GetType() return 1 data thuộc kiểu Type.

- Lớp Type là lớp cung cấp 1 số methods để lấy thông tin của 1 đối tượng: GetMethod(), GetFields(), GetProperties(), ... trong thời gian chạy ( runtime ).

--- Attribute/Annotation trong C#

- Attribute là 1 thẻ khai báo. Attribute cho phép gán metadata vào lớp, phương thức hoặc thuộc tính những đoạn code mở rộng. Hay nói cách khác Attribute thêm metadata vào type.

- Metadata là các thông tin mô tả về cấu trúc và đặc điểm của các loại (types), phương thức, thuộc tính, sự kiện, ràng buộc và các thành phần khác của một chương trình hoặc một assembly. Meta có thể được dùng để validate input của 1 class

- 1 số Attribute được build-in trong .NET, [required()], [StringLength()], [DataType()], ...

- 1 custom class attribute phải devired từ Attribute base class.

- Các object chỉ được dùng làm Attribute Type Parameter: string, bool, hoặc numeric types, Enums, Type, Mảng 1 chiều.

--- Using trong C#

- using được sử dụng để tạo một phạm vi có giới hạn cho một đối tượng và đảm bảo rằng đối tượng sẽ được giải phóng ngay sau khi phạm vi đó kết thúc.

--- Preprocessor Directives (Những chỉ thị tiền xử lý) trong C#

- Preprocessor Directives (Những chỉ thị tiền xử lý) trong C# là các commands được xử lý bởi trình biên dịch trước khi quá trình biên dịch thực sự bắt đầu. Chúng được sử dụng để kiểm soát việc biên dịch của mã nguồn dựa trên các điều kiện được xác định trước. Một trong những mục đích phổ biến của chúng là để kiểm soát các cảnh báo (warnings) mà chúng ta muốn thấy trong quá trình biên dịch.

- 1 số PD thường dùng: #warning, #error, #nullable disable, #nullable enable, ...

--- Task trong c#

- Task là một loại dữ liệu đại diện cho một tác vụ (hoặc một công việc) được thực thi bất đồng bộ. Task cung cấp một cơ chế để theo dõi tiến trình và kết quả của tác vụ.

- Khi bạn sử dụng async, phương thức của bạn thường sẽ trả về một đối tượng Task để biểu diễn kết quả của tác vụ đó. Task có thể trả về một giá trị (ví dụ: Task<string>) hoặc không trả về giá trị (ví dụ: Task).

- Task cung cấp các phương thức và thuộc tính để theo dõi trạng thái của tác vụ, như IsCompleted, IsFaulted, Result,...

- Params keyword trong C#

- Trong C#, từ khóa params được sử dụng để khai báo một method với một số lượng đối số không xác định được truyền vào. Điều này có nghĩa là bạn có thể truyền vào một số lượng biến đối số không giới hạn khi gọi phương thức đó.

- VD: public void Calculator(params int[] numbers) { }

--- Yield Statement trong C#

- Yield statement trong C# được sử dụng để tạo ra một từ một phương thức. Iterator là một object cho phép bạn duyệt qua một tập hợp các phần tử một cách tuần tự.

- Nếu 1 method có yield statement bên trong, method đó trở thành 1 iterator method. Khi gọi một iterator method, code bên trong phương thức không được thực thi ngay lập tức. Thay vào đó, phương thức trả về một đối tượng iterator mới, mà sau đó có thể được sử dụng để duyệt qua các phần tử một cách tuần tự. Một iterator luôn luôn tiếp tục tại nơi mà nó kết thúc lần trước.

- Khi sử dụng yield, bạn có thể trả về từng phần tử của tập hợp một cách lười biếng, có nghĩa là phần tử sẽ được tính toán và trả về chỉ khi cần thiết. Điều này cho phép bạn làm việc với các tập hợp lớn mà không cần phải tạo ra toàn bộ tập hợp trước.

--- Checked keyword trong C#

- Từ khóa checked defined một scope mà trong đó các toán tử toán học sẽ được kiểm tra để đảm bảo không xảy ra hiện tượng numeric overflow. Nếu xảy ra thì sẽ throw OverflowExeception(). VD: try { checked { z = x + y; } } catch(OverflowException ex) {}

- Checked Scope có thể gây ảnh hưởng tới performance.

- Numeric Overflow là hiện tượng mà một biến numeric type chứa 1 giá trị vượt quá sức chứa của nó.

--- Event trong C#

- Event trong C# là 1 cơ chế thông báo cho các class khác rằng 1 hành động đã xảy ra.

- Event phải được khai báo như 1 field, không phải 1 thuộc tính. Một biến event có thể được xem như 1 mutilcast delegate vì nó có thể tham chiếu tới nhiều methods của các observer object. Event khác với 1 field thuộc type delegate ở chỗ là event chỉ có thể được invoke() ở bên trong class chứa nó còn biến delagate có thể được gọi ở bất kì đâu tùy thuộc vào access modifier.

- Event implement Observer Design Pattern. Mechanism của Event đựa trên việc dùng delegates.

- Method Invoke() được sử dụng để gọi tất cả các phương thức đăng ký với sự kiện đó. Đây là một cách để kích hoạt sự kiện và gửi thông điệp đến tất cả các đăng ký. Khi bạn gọi Invoke(), tất cả các phương thức đăng ký được gọi tuần tự.

- EventHandler là một kiểu delegate được tích hợp sẵn trong .NET chuyên sử dụng để khai báo và tạo ra các sự kiện ( events ).

- EventHandler ~ delegate void Name(object? sender, EventArgs e). Tham số sender: Đây là đối tượng gửi sự kiện. Thường thì nó là đối tượng mà sự kiện được kích hoạt từ đó. Tham số e: Đây là đối tượng chứa thông tin về sự kiện. Thông thường, nó là một đối tượng của lớp EventArgs hoặc một lớp con của EventArgs.

--- Null-Propagating operator trong C#: Giống toán tử ?. trong JS

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
