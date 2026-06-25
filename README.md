# Pacman AI Search Project

## Giới thiệu

Đây là dự án cài đặt các thuật toán tìm kiếm trong lĩnh vực Trí tuệ nhân tạo (Artificial Intelligence) thông qua trò chơi Pacman.

Mục tiêu của dự án là áp dụng các thuật toán tìm kiếm để giúp Pacman tìm đường đi trong mê cung và giải quyết các bài toán khác nhau trong môi trường game.

Dự án được xây dựng dựa trên framework của môn CS188 - Artificial Intelligence.

---

## Chức năng chính

Các thuật toán tìm kiếm đã được cài đặt:

* Tìm kiếm theo chiều sâu (Depth First Search - DFS)
* Tìm kiếm theo chiều rộng (Breadth First Search - BFS)
* Tìm kiếm chi phí thấp nhất (Uniform Cost Search - UCS)
* Tìm kiếm A* (A Star Search)

Các bài toán mở rộng:

* Corners Problem: Tìm đường đi qua tất cả các góc của mê cung
* Food Search Problem: Tìm đường ăn toàn bộ thức ăn
* Heuristic Optimization: Tối ưu hàm đánh giá cho thuật toán A*

---

## Cấu trúc thư mục

```text
search/
│
├── pacman.py              # File chính để chạy game
├── search.py              # Cài đặt các thuật toán tìm kiếm
├── searchAgents.py        # Các Agent sử dụng thuật toán search
├── game.py                # Bộ máy xử lý game
├── util.py                # Các cấu trúc dữ liệu hỗ trợ
│                           (Stack, Queue, Priority Queue)
│
├── layouts/               # Các bản đồ mê cung
│
└── test_cases/            # Các file kiểm tra kết quả
```

---

## Yêu cầu môi trường

* Python 3.x

Không yêu cầu cài đặt thêm thư viện ngoài.

---

## Cách chạy chương trình

### Chạy thuật toán DFS

```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=dfs
```

### Chạy thuật toán BFS

```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=bfs
```

### Chạy thuật toán UCS

```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=ucs
```

### Chạy thuật toán A*

```bash
python pacman.py -l bigMaze -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic
```

---

## Kiểm tra chương trình

Chạy toàn bộ bộ kiểm tra:

```bash
python autograder.py
```

Kiểm tra từng câu:

Ví dụ kiểm tra câu 1:

```bash
python autograder.py -q q1
```

Kiểm tra thuật toán A*:

```bash
python autograder.py -q q4
```

---

# Mô tả thuật toán

## 1. DFS (Depth First Search)

Thuật toán tìm kiếm theo chiều sâu.

* Sử dụng cấu trúc dữ liệu Stack.
* Luôn ưu tiên đi sâu nhất có thể trước.

Ưu điểm:

* Cài đặt đơn giản.
* Có thể tìm thấy đường đi nhanh trong một số trường hợp.

Nhược điểm:

* Không đảm bảo đường đi ngắn nhất.

---

## 2. BFS (Breadth First Search)

Thuật toán tìm kiếm theo chiều rộng.

* Sử dụng Queue.
* Duyệt các nút theo từng lớp.

Ưu điểm:

* Tìm được đường đi ngắn nhất khi chi phí mỗi bước bằng nhau.

Nhược điểm:

* Tốn nhiều bộ nhớ.

---

## 3. UCS (Uniform Cost Search)

Thuật toán tìm kiếm theo chi phí nhỏ nhất.

Công thức:

```
f(n) = g(n)
```

Trong đó:

* g(n): chi phí từ điểm bắt đầu đến trạng thái hiện tại.

Thuật toán luôn chọn trạng thái có chi phí thấp nhất để mở rộng.

---

## 4. A* Search

Thuật toán kết hợp giữa chi phí đã đi và dự đoán khoảng cách còn lại.

Công thức:

```
f(n) = g(n) + h(n)
```

Trong đó:

* g(n): chi phí đã đi.
* h(n): giá trị heuristic dự đoán.
* f(n): tổng giá trị đánh giá.

A* giúp tìm đường đi tối ưu với tốc độ nhanh hơn so với UCS trong nhiều trường hợp.

---

## Tác giả

Project thực hiện nhằm mục đích học tập và nghiên cứu các thuật toán tìm kiếm trong Trí tuệ nhân tạo.

---

##Link báo cáo
https://drive.google.com/file/d/1dkkBR13hBuP9N0GS1nrdXt0DZYNSQKyW/view?usp=drive_link
