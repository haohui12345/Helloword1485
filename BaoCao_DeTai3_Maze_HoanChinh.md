Đề tài: Tìm Đường Thoát Thông Minh Trong Trò Chơi Mê Cung

1. Lý do chọn đề tài

Trong lĩnh vực trí tuệ nhân tạo và lập trình thuật toán, bài toán tìm đường trong mê cung là một trong những bài toán cơ bản nhưng vô cùng quan trọng. Không chỉ có ý nghĩa trong game, nó còn mang tính ứng dụng cao trong robot di động, dẫn đường tự động, và hệ thống bản đồ.

Việc mô phỏng trò chơi mê cung giúc người học tiếp cận gần hơn với các thuật toán tìm kiếm như BFS, DFS, Dijkstra và đặc biệt là A*, đồng thời áp dụng được tư duy tối ưu hóa, trực quan hóa bằng đồ họa với HTML5 và Canvas.

2. Mục tiêu của đề tài

Xây dựng hệ thống sinh mê cung ngẫu nhiên sử dụng thuật toán Kruskal.

Tìm đường đi ngắn nhất từ điểm bắt đầu đến điểm kết thúc bằng thuật toán A*.

Hiển thị đường đi tối ơu lên giao diện đồ họa Canvas.

Cho phép người chơi tương tác, điều khiển, thu thập vật phẩm.

Cung cấp tính năng tự động giải mê cung và phân tích bước đi.

3. Tổng quan kiến trúc chương trình

3.1 Các thành phần chính

maze: lớp đối tượng xử lý sinh mê cung.

astar: thuật toán tìm đường.

draw_canvas: vẽ mê cung lên HTML5 canvas.

autoMovePlayer: điều hướng tự động theo đường đi tìm được.

Giao diện được thiết kế bằng HTML, CSS, JavaScript thuần.

3.2 Cấu trúc giao diện

Canvas dùng để hiển thị mê cung và các đối tượng như tường, đường đi, vật phẩm, người chơi.

Các nút chọn cấp độ, nút bắt đầu và giải mê cung.

Thông tin vật phẩm, thời gian và số bước hiển thị rõ ràng.

4. Thuật toán sinh mê cung: Kruskal + Union-Find

4.1 Mô tả

Mỗi ô là một node, các bức tường giữa hai ô liền kề là các cạnh.

Dùng Union-Find để nối các vùng không liên thông.

Chỉ phá tường nếu hai ô chưa cùng tập hợp → đảm bảo không tạo chu trình.

4.2 Các bước thực hiện

Gán mỗi ô là một tập riêng.

Sinh danh sách các cạnh (tường).

Trộn ngẫu nhiên danh sách cạnh.

Với mỗi cạnh:

Nếu hai ô chưa cùng tập → phá tường nối hai ô lại, thực hiện union.

Kết thúc khi toàn bộ ô đã nối thành một mê cung liên thông.

5. Thuật toán tìm đường A* (A-Star)

5.1 Khái niệm

A* là thuật toán tìm đường ngắn nhất sử dụng hàm heuristic để ước lượng chi phí còn lại. Đây là thuật toán rất hiệu quả vì kết hợp được giữa tìm kiếm theo chi phí (g) và dự đoán (h).

5.2 Công thức

f(n) = g(n) + h(n)

Trong đó:

g(n): chi phí từ điểm bắt đầu đến điểm hiện tại.

h(n): chi phí ước lượng từ điểm hiện tại đến đích.

5.3 Hàm heuristic

Manhattan: abs(x1 - x2) + abs(y1 - y2)

Euclidean: sqrt((x1 - x2)^2 + (y1 - y2)^2)

5.4 Các bước thực hiện

Thêm điểm bắt đầu vào openSet.

Lặp:

Chọn ô có fScore nhỏ nhất.

Nếu là đích → trả về đường đi.

Duyệt các ô hàng xóm:

Nếu chưa được xét và là đường hợp lệ → tính g, f, cập nhật cameFrom.

Khi đến được goal, dựng lại đường đi từ cameFrom.

6. Điều khiển và tương tác

Người chơi có thể di chuyển bằng phím mũi tên hoặc W/A/S/D.

Mỗi khi đi qua vật phẩm, sẽ được thu thập và hiển thị trên thanh trạng thái.

Khi đủ vật phẩm, người chơi có thể đi tới đích để chiến thắng.

Nếu chưa đủ vật phẩm, hệ thống sẽ báo lỗi và không cho kết thúc.

7. Vẽ đường đi tối ơu

Sau khi thuật toán A* tìm được đường đi:

Vẽ lại mê cung.

Dùng màu khác (xanh cyan) để hiển thị đường đi.

In ra tọa độ đường đi nếu cần.

Nếu người chơi chọn tự động, hệ thống sẽ lần lượt di chuyển qua các bước.

8. Giao diện và trải nghiệm người dùng

Giao diện đẹp mắt, dễ thao tác.

Gradient nền và hiệu ứng màu làm nổi bật các vùng quan trọng.

Responsive tốt, hỗ trợ cả trên thiết bị nhỏ.

Cung c

