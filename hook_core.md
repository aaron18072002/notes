-- State là gì

- State là một giá trị động mà component cần render ra UI, một giá trị mà có thể thay đổi theo thời gian ( bởi chính sự tương tác của user hay logic trong component ). Và khi state thay đổi, component sẽ re-render lại để luôn giữ cho UI đồng bộ với giá trị của state. Để user luôn có thể đọc và tương tác với state mới nhất.

-- Khi nào dùng state

- Dùng state khi chúng ta cần 1 giá trị chỉ có thể thuộc về bởi component chứa nó. Và state đó chỉ có thể thay đổi bởi người dùng tương tác với component đó ở phía UI hay logic trong component đó. Và component đó cần phải nhớ và giữ state đó theo thời gian xuyên xuốt app's lifecycle. Chỉ khi component đó unmount và được mount lại thì các state mới được set lại giá trị ban đầu.

-- Các kiểu state

- State đồng bộ, bất đồng độ ( data được get từ API sau đó set vào state để render ra UI ).
- Local state, Global State ( Redux, Context API, ... ).

-- So sánh Local State và Global State

1. Local State

- Local State là những state chỉ thuộc về 1 hoặc 1 ít components.
- Local State là những state chỉ được khai báo trong 1 component và chỉ component đó hoặc 1 vài component con là được quyền truy cập đến các state đó.

2. Global State

- Global State là các state mà nhiều components cần sử dụng.
- Global State là state được đặt ở nơi mà nhiều hoặc tất cả components đều có thể truy cập được.

-- Cách hoạt động của useState

- useState không có 1 lifecycle riêng biệt như class component với các lifecycle methods như componentDidMount, componentWillMount.
- Initialization: Khi 1 component lần đầu được mount, useState sẽ gán giá trị ban đầu ( initial value ) cho state nằm trong component đó.
- Rendering: Mỗi khi state được thay đổi bởi setState, component sẽ re-render lại để giữ cho giá trị của state đó đồng bộ với UI ở phía người dùng.
- Dependency: state cũng có thể dùng làm các dependency cho useEffect, useCallback,... để khi state đó thay đổi thì logic trong các hook đó sẽ được chạy lại để xử lý.

-- So sánh useCallback và useMemo

- Cả 2 đều ghi nhớ giá trị giữa các lần mà component re-render
- useMemo sẽ ghi nhớ value khi hàm đó trả về giá trị tham trị, còn nếu trả về giá trị tham chiếu thì useMemo sẽ ghi nhớ địa chỉ.
- Còn useCallback sẽ ghi nhớ 1 reference tới hàm đó.

-- Vì sao useCallback hay đi chung với HOC memo trong reactjs

- Đảm bảo rằng các hàm callback được truyền xuống các component con chỉ được tạo lại khi các dependencies của chúng thay đổi. Bởi vì nếu chỉ sử dụng memo mà không sử dụng useCallback thì các hàm callback được truyền từ component cha vẫn sẽ bị chạy lại khi component cha re-render.
