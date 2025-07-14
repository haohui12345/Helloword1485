
# BÁO CÁO ĐỀ TÀI: TÌM ĐƯỜNG THOÁT THÔNG MINH TRONG TRÒ CHƠI MÊ CUNG

---

## MỞ BÀI

### 1. Lý do chọn đề tài
Trong thời đại hiện nay, các bài toán về tìm đường đi trong môi trường phức tạp không chỉ ứng dụng trong game mà còn liên quan đến robot, logistics, và trí tuệ nhân tạo. Trò chơi mê cung là một mô hình đơn giản nhưng rất gần gũi để mô phỏng các bài toán đó. Việc sử dụng thuật toán A* – một thuật toán tìm kiếm có heuristic – giúp tối ưu hóa quá trình tìm đường, từ đó nâng cao hiệu suất và tính thông minh của hệ thống.

### 2. Mục tiêu đề tài
- Xây dựng hệ thống mê cung tương tác trực quan bằng HTML5/JavaScript.
- Áp dụng thuật toán A* để tìm đường đi ngắn nhất từ điểm bắt đầu (S) đến điểm kết thúc (G).
- Hiển thị đường đi tối ưu và hỗ trợ điều khiển nhân vật thủ công hoặc tự động.
- Phát triển một hệ thống mở có thể mở rộng thêm trong tương lai.

---

## THÂN BÀI

### 3. Tổng quan hệ thống

#### 3.1 Ngôn ngữ và công nghệ sử dụng
- HTML5: Dùng để tạo khung và canvas.
- CSS3: Dùng để thiết kế giao diện người dùng thân thiện.
- JavaScript (thuần): Xử lý logic game, sinh mê cung, thuật toán tìm đường, sự kiện người dùng.
- Canvas API: Vẽ mê cung, nhân vật, đường đi.

#### 3.2 Cấu trúc hệ thống
- `index.js`: Gồm toàn bộ logic của game và các thuật toán.
- `style.css`: Định dạng giao diện, màu sắc, bố cục.
- `canvas`: Khu vực tương tác chính, nơi vẽ mê cung và xử lý tương tác.

---

### 4. Phân tích chức năng chi tiết

#### 4.1 Khởi tạo mê cung
- Thuật toán sinh mê cung sử dụng Kruskal kết hợp Union-Find để đảm bảo toàn bộ mê cung là một đồ thị liên thông.
- Mỗi ô trong mê cung là một đỉnh, các tường là cạnh.
- Các bước:
  1. Khởi tạo từng ô là một tập riêng biệt.
  2. Tạo danh sách các tường giữa các ô liền kề.
  3. Trộn ngẫu nhiên danh sách cạnh.
  4. Duyệt danh sách, nối những ô chưa cùng tập hợp.

#### 4.2 Giao diện và điều khiển
- Canvas sẽ vẽ các đối tượng:
  - Tường: màu xanh đậm
  - Đường đi: trắng
  - Vật phẩm: tím
  - Người chơi: đỏ
  - Start: xanh lá
  - Goal: vàng
- Người chơi điều khiển bằng phím: `↑ ↓ ← →` hoặc `W A S D`.

#### 4.3 Thêm vật phẩm ngẫu nhiên
- Tại mỗi mê cung được tạo ra, sẽ có các vật phẩm được đặt tại các ô trống ngẫu nhiên.
- Người chơi cần **thu thập hết** vật phẩm mới được đi tới đích.

---

### 5. Thuật toán A* (A-Star)

#### 5.1 Giới thiệu A*
- A* là thuật toán tìm kiếm sử dụng hàm heuristic để ước lượng chi phí từ điểm hiện tại đến đích.
- Nó đảm bảo tìm được đường đi ngắn nhất (trong môi trường không có trọng số âm).

#### 5.2 Công thức:
```
f(n) = g(n) + h(n)
```
- `g(n)`: Chi phí thực từ start đến `n`
- `h(n)`: Ước lượng chi phí từ `n` đến goal

#### 5.3 Hàm heuristic sử dụng
- **Manhattan**: Ưu tiên cho lưới ô vuông
- **Euclidean**: Mô phỏng đường thẳng thực tế

#### 5.4 Triển khai trong chương trình
- `astar()`: Hàm chính cài đặt thuật toán A*.
- `solveMaze()`: Gọi hàm `astar()`, vẽ lại mê cung và hiển thị đường đi.
- `autoMovePlayer()`: Sau khi có đường đi, hệ thống sẽ tự động điều hướng người chơi.

---

### 6. Giao diện người dùng

#### 6.1 Tổng quan
- Tạo cảm giác hiện đại, trẻ trung bằng gradient màu sắc và hiệu ứng CSS.
- Dễ thao tác và điều hướng.

#### 6.2 Các thành phần chính
- Combo box chọn cấp độ (5x5, 10x10, 15x15).
- Nút “Giải” để chạy thuật toán tìm đường.
- Hiển thị vật phẩm đã thu thập, thời gian còn lại, số bước đã đi.

---

### 7. Kiểm thử & Demo

#### 7.1 Tình huống bình thường
- Người chơi thu thập đủ vật phẩm và đi đến đích.
- Đường đi được vẽ bằng màu cyan nhạt (đường A*).

#### 7.2 Trường hợp không có đường thoát
- Hệ thống hiển thị cảnh báo: “Không có đường thoát!”

#### 7.3 Trường hợp chưa đủ vật phẩm
- Khi người chơi đến đích nhưng thiếu vật phẩm, hệ thống hiển thị cảnh báo và không kết thúc game.

---

## KẾT LUẬN

### 8. Đánh giá kết quả đạt được

- ✅ Đã triển khai đầy đủ thuật toán A*.
- ✅ Giao diện đẹp, có thể chạy thực tế trên trình duyệt.
- ✅ Tương tác tốt với người dùng.
- ✅ Hỗ trợ tự động giải và mô phỏng đường đi rõ ràng.

### 9. Hạn chế

- Mỗi ô có chi phí bằng nhau – chưa hỗ trợ chi phí khác nhau.
- Mê cung chưa thay đổi được theo thời gian thực (mê cung động).
- Giao diện chưa có tính năng thiết kế mê cung bằng tay.

### 10. Hướng phát triển

- ✅ Hỗ trợ chi phí khác nhau cho mỗi ô.
- ✅ Hỗ trợ mê cung động.
- ✅ So sánh heuristic khác nhau trong thời gian thực.
- ✅ Tạo trình thiết kế mê cung trực quan.
- ✅ Ứng dụng cho mô hình robot thật.

---

## PHỤ LỤC

### A. Một số ảnh minh họa (nếu có thể trình chiếu)
### B. Mã nguồn: đã chia theo từng hàm rõ ràng
### C. Tài liệu tham khảo:
- Wikipedia – A* algorithm
- StackOverflow – Canvas Pathfinding
- Giáo trình Trí tuệ nhân tạo – Đại học KHTN
