- GIT BRANCH

-- Nếu bạn tạo 1 branch mới trên một branch khác, thì tất cả commits trên cái branch khác đó sẽ được đưa vào branch mới.

- HEAD

-- HEAD là một con trỏ đại diện cho commit mới nhất của branch hiện tại mà bạn đang làm việc. Khi bạn thực hiện các lệnh như git commit, git checkout, hoặc git reset, Git sẽ sử dụng HEAD để xác định vị trí của commit hiện tại.

-- Nếu bạn đang ở trên một branch cụ thể (ví dụ, main), HEAD sẽ trỏ đến commit mới nhất trên branch main.

-- Nếu bạn chuyển sang commit cụ thể không thuộc branch nào (trạng thái “detached HEAD”), HEAD sẽ trỏ trực tiếp đến commit đó, thay vì trỏ đến một branch.
