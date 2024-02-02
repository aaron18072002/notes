-- useContext và redux

- Với useContent, khi state thay đổi thì sẽ re-render lại toàn bộ components đang dùng context đó.
- Với redux thì chỉ re-render các components có data thay đổi.

-- Các khái niệm của redux

- Action trong Redux chỉ là các hàm trả về một object chứa type và payload { type, payload }. Và ta sẽ dispatch action đó vào hàm reducer trong store xử lý để update state theo như type của action đó trả về với swich case trong reducer.
- Middlware trong Redux là 1 hàm nằm giữa action được dispatch và store chứa reducer.
- Mục đích của middleware trong redux là xử lý các action được dispatch trước khi nó được reducer xử lý.
- Redux toolkit nó sẽ thiên về các state của client (đồng bộ) còn với những thằng bất đồng bộ thì phải dùng middleware (saga, thunk) để quản lí nó.

-- Redux vs Redux Toolkit

- Redux toolkit là 1 phiên bản nâng cấp của Redux. Trong Redux Toolkit, ta dùng function createSlice( ) mà nó cung cấp để tạo actions và reducer thay cho việc phải tạo các file actions và reducer trong Redux.

-- Redux Thunk và Redux Saga

- Cả 2 đều là middleware để xử lý các state bất đồng bộ trong redux
- Middleware trong redux chỉ là một hàm để xử lý các actions được dispatch trước khi reducer xử lý actions đó.
- Redux Thunk sử dụng các thunk function để xử lý các actions liên quan tới side effect ( gọi API ). Thunk function đơn giản chỉ là một hàm gọi lại hàm action được dispatch đó với các tham số dispatch.
- Redux Saga thì dùng generator function để xử lý.
