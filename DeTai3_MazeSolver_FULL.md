
# Đề tài 3: Tìm Đường Thoát Thông Minh Trong Trò Chơi Mê Cung

---

## 1. Giới thiệu

### Mô tả bài toán
Trong trò chơi mê cung, người chơi hoặc robot cần phải tìm đường đi ngắn nhất từ điểm bắt đầu (S) đến điểm kết thúc (G) trong một mê cung 2D. Mỗi mê cung có thể bao gồm:
- Tường không thể đi qua
- Các đường đi trống
- Các vật phẩm cần thu thập
- Điểm bắt đầu `$` và điểm đích `G`

Chúng ta cần sử dụng thuật toán tìm kiếm thông minh có heuristic như **A* (A-Star)** để giải quyết bài toán tìm đường ngắn nhất. 

---

## 2. Công nghệ và công cụ sử dụng

- **Ngôn ngữ lập trình**: JavaScript (thuần)
- **Công cụ hiển thị**: HTML5 Canvas
- **CSS**: Thiết kế giao diện trực quan với màu sắc bắt mắt
- **Thuật toán chính**: Sinh mê cung (Kruskal's algorithm + Union-Find), tìm đường A*

---

## 3. Các thành phần chính trong chương trình

### a. Cấu trúc tổng thể
- `index.js`: Toàn bộ logic game và thuật toán
- `style.css`: Giao diện và trình bày đồ họa
- `canvas`: Khu vực chính để vẽ mê cung và đường đi

### b. Luồng hoạt động
1. **Sinh mê cung**
2. **Thêm vật phẩm**
3. **Hiển thị mê cung**
4. **Di chuyển nhân vật (thủ công hoặc tự động)**
5. **Tìm đường tối ưu bằng A\* và hiển thị**
6. **Kết thúc khi đến được đích và thu đủ vật phẩm**

---

## 4. Thuật toán và chức năng chi tiết

### a. Sinh mê cung: Kruskal + Union-Find
- Khởi tạo mỗi ô là một tập riêng biệt.
- Sinh ra danh sách các cạnh (liên kết giữa ô).
- Trộn danh sách cạnh ngẫu nhiên.
- Sử dụng Union-Find để phá tường nối các vùng chưa liên thông.
- Đảm bảo mê cung có ít nhất một đường duy nhất từ S → G.

### b. Thuật toán A* (A-Star)
- Áp dụng cho bài toán tìm đường trong mê cung có chi phí đều.
- Mỗi bước, ta mở rộng ô có tổng chi phí nhỏ nhất:
  ```
  f(n) = g(n) + h(n)
  ```
  Trong đó:
  - `g(n)`: Chi phí từ S đến n (số bước)
  - `h(n)`: Hàm heuristic đến G (Manhattan hoặc Euclidean)

### c. Heuristic
- **Manhattan**: |x1 - x2| + |y1 - y2|
- **Euclidean**: √((x1 - x2)² + (y1 - y2)²)

### d. Hiển thị mê cung
- Tường: màu tối
- Đường đi: trắng
- Vật phẩm: tím
- Start: xanh lá
- Goal: vàng
- Người chơi: đỏ

---

## 5. Các tính năng nổi bật

| Tính năng                          | Mô tả |
|-----------------------------------|-------|
| Đa cấp độ                          | Dễ (5x5), Trung bình (10x10), Khó (15x15) |
| Thuật toán sinh mê cung            | Kruskal với Union-Find |
| Vật phẩm ngẫu nhiên                | Thu thập đủ mới được đến đích |
| Tự động giải mê cung               | Bằng A* với lựa chọn heuristic |
| Hiển thị trực quan                 | Canvas động với hiệu ứng màu |
| Thống kê thời gian và số bước      | Có đồng hồ đếm ngược, cập nhật số bước |
| Tự động di chuyển theo đường đi   | Sau khi tìm ra đường A* |
| Mê cung mẫu hardcoded              | Có thể so sánh giữa mê cung tạo ngẫu nhiên và cố định |

---

## 6. Giao diện người dùng (theo file style.css)

- **Màu nền gradient** dịu mắt, hiện đại.
- **Các khối thông tin** được bo góc, đổ bóng mờ nhẹ.
- **Nút điều khiển** tương tác với hiệu ứng hover mượt.
- **Canvas** là trung tâm tương tác, được bo góc và viền nổi bật.
- **Responsive** với cả PC và mobile.

---

## 7. Kết quả và demo minh họa

Khi chạy chương trình:
- Người dùng chọn độ khó.
- Game tự sinh mê cung và vật phẩm.
- Di chuyển bằng phím mũi tên/WASD.
- Khi bấm “Giải”, thuật toán A* sẽ tìm đường đi tối ưu và vẽ lên canvas.
- Nếu người chơi đủ vật phẩm và đến G → **Thắng**.

**Tình huống không có đường thoát**: Chương trình sẽ hiển thị “Không có đường thoát!” một cách trực quan.

---

## 8. Đánh giá và mở rộng

### a. Điểm mạnh
- Tốc độ giải nhanh (do tối ưu bằng A*).
- Giao diện sinh động, dễ sử dụng.
- Có thể mở rộng cho robot thực tế.

### b. Hướng mở rộng
- Tính năng chi phí mỗi ô khác nhau (dijkstra + A*).
- Tường di động, mê cung thay đổi theo thời gian.
- Thuật toán học đường đi (machine learning reinforcement).
- Tạo trình biên tập mê cung để người dùng thiết kế.
- So sánh hiệu năng giữa nhiều thuật toán (BFS, DFS, A*, IDA*...).

---

## 9. Tổng kết

Đề tài “Tìm đường thoát thông minh trong mê cung” là một ứng dụng thú vị của AI và thuật toán tìm kiếm. Qua việc kết hợp giữa:
- **Tư duy giải thuật**
- **Kỹ thuật lập trình**
- **Giao diện người dùng đẹp mắt**

Nó mang lại trải nghiệm học tập, giải trí và thực hành tốt cho sinh viên ngành CNTT hoặc AI. Hệ thống hoàn toàn có thể phát triển thêm để phục vụ mục đích nghiên cứu và thực nghiệm thực tế.

