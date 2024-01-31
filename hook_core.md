-- So sánh useCallback và useMemo

- Cả 2 đều ghi nhớ giá trị giữa các lần mà component re-render
- useMemo sẽ ghi nhớ value khi hàm đó trả về giá trị tham trị, còn nếu trả về giá trị tham chiếu thì useMemo sẽ ghi nhớ địa chỉ.
- Còn useCallback sẽ ghi nhớ 1 reference tới hàm đó.
