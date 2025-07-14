
# Đề tài 3: Tìm đường thoát thông minh trong trò chơi mê cung

## 1. Giới thiệu đề tài

Trong trò chơi mê cung, người chơi cần tìm đường thoát ngắn nhất từ điểm bắt đầu (S) đến điểm kết thúc (G). Đề tài sử dụng thuật toán tìm kiếm A* (A-star) để giải bài toán này. Thuật toán sử dụng hàm heuristic để ước lượng chi phí còn lại từ một điểm đến đích, giúp tìm được đường đi tối ưu với chi phí nhỏ nhất.

---

## 2. Cấu trúc chương trình

Chương trình được xây dựng gồm các phần chính:

- Khởi tạo mê cung sử dụng thuật toán Kruskal (Union-Find).
- Tạo các cấp độ mê cung (dễ, trung bình, khó).
- Cài đặt thuật toán A* với lựa chọn heuristic (Manhattan hoặc Euclidean).
- Giao diện canvas hiển thị mê cung, người chơi, vật phẩm và đường đi.
- Tự động vẽ đường đi tối ưu và di chuyển nhân vật theo đường đi đó.

---

## 3. Mô tả thuật toán và chức năng

### a. Sinh mê cung (Kruskal + Union-Find)

- Khởi tạo các ô.
- Sinh danh sách các tường giữa các ô liền kề.
- Ngẫu nhiên trộn danh sách tường.
- Gộp các vùng không liên thông để tạo mê cung hoàn chỉnh.

### b. A* (A-star) pathfinding

- Sử dụng hàm `manhattan()` hoặc `euclidean()` làm heuristic.
- Luôn chọn ô có tổng chi phí (gScore + heuristic) thấp nhất.
- Dựng lại đường đi từ đích về đầu khi tìm thấy.

### c. Vẽ và cập nhật mê cung

- Canvas hiển thị mê cung dưới dạng lưới.
- Các màu sắc phân biệt: tường, đường đi, vật phẩm, điểm bắt đầu, điểm kết thúc.
- Đường đi tối ưu được tô nổi bật khi giải xong.

---

## 4. Các chức năng chính

| Chức năng                    | Mô tả                                                                 |
|-----------------------------|----------------------------------------------------------------------|
| `startGame()`               | Khởi tạo mê cung và bắt đầu trò chơi                                 |
| `solveMaze()`               | Giải mê cung hiện tại và vẽ đường đi                                 |
| `astar()`                   | Cài đặt thuật toán A* để tìm đường đi ngắn nhất                      |
| `drawOptimalPath()`         | Tô màu đường đi tối ưu trên mê cung                                  |
| `autoMovePlayer()`          | Tự động di chuyển người chơi theo đường đi đã tìm được               |
| `addItemsToMaze()`          | Thêm vật phẩm ngẫu nhiên vào mê cung                                 |

---

## 5. Các yêu cầu đã hoàn thành

- [x] Đọc mê cung từ ma trận hoặc tạo tự động.
- [x] Tìm đường đi từ S đến G bằng thuật toán A*.
- [x] Hiển thị đường đi trên bản đồ.
- [x] Xử lý trường hợp không có đường thoát.
- [x] Thu thập vật phẩm bắt buộc trước khi đến đích.

---

## 6. Hướng mở rộng

- [ ] Chi phí di chuyển khác nhau cho mỗi ô.
- [ ] Mê cung động – vật cản thay đổi theo thời gian.
- [ ] So sánh hiệu năng giữa các heuristic khác nhau.
- [ ] Hiển thị quá trình tìm đường theo thời gian thực.
- [ ] Bổ sung các vật phẩm cần thu thập (đã có một phần).

---

## 7. Kết luận

Thuật toán A* cùng với mô hình hóa mê cung bằng canvas JavaScript là một cách tiếp cận hiệu quả để tìm đường đi tối ưu trong trò chơi mê cung. Giao diện trực quan và khả năng mở rộng cao giúp dự án phù hợp cho cả học tập và giải trí.

