-- State là gì

-- Khi nào dùng state

- Dùng state khi chúng ta cần 1 giá trị chỉ có thể thuộc về bởi component chứa nó. Và state đó chỉ có thể thay đổi bởi người dùng tương tác với component đó ở phía UI hay logic trong component đó. Và component đó cần phải giữ state đó theo thời gian và xuyên xuốt app's lifecycle.

-- Các kiểu state

-- So sánh useCallback và useMemo

- Cả 2 đều ghi nhớ giá trị giữa các lần mà component re-render
- useMemo sẽ ghi nhớ value khi hàm đó trả về giá trị tham trị, còn nếu trả về giá trị tham chiếu thì useMemo sẽ ghi nhớ địa chỉ.
- Còn useCallback sẽ ghi nhớ 1 reference tới hàm đó.

-- Cách hoạt động của useState

- useState không có 1 lifecycle riêng biệt như class component với các lifecycle methods như componentDidMount, componentWillMount.
- Initialization: Khi 1 component lần đầu được mount, useState sẽ gán giá trị ban đầu ( initial value ) cho state nằm trong component đó.
- Rendering: Mỗi khi state được thay đổi bởi setState, component sẽ re-render lại để giữ cho giá trị của state đó đồng bộ với UI ở phía người dùng.
- Dependency: state cũng có thể dùng làm các dependency cho useEffect, useCallback,... để khi state đó thay đổi thì logic trong các hook đó sẽ được chạy lại để xử lý.
