# Hệ thống quản lí sinh viên

## Công nghệ sử dụng
- Frontend: React + Vite
- Backend: Node.js + Express
- Database: SQLite (file `backend/school.db` tự tạo khi chạy)
- Xác thực: JWT
- Phân quyền: `admin`, `lecturer`, `student`

## Chức năng hiện có
### Xác thực
- Đăng ký tài khoản `lecturer` hoặc `student`
- Đăng nhập / đăng xuất
- Phân quyền theo vai trò sau khi đăng nhập

### Admin
- Xem thống kê hệ thống
- Quản lý tài khoản người dùng
- Thêm / sửa / xóa hồ sơ sinh viên
- Nhập / sửa / xóa điểm số
- Tạo / sửa / xóa lịch học

### Lecturer
- Xem thống kê học tập
- Cập nhật hồ sơ sinh viên
- Nhập / sửa / xóa điểm số
- Tạo / sửa / xóa lịch học

### Student
- Xem thông tin cá nhân
- Xem bảng điểm cá nhân
- Xem lịch học theo lớp
- Xem thẻ thống kê nhanh trên dashboard

## Cách chạy project
### 1) Cài package ở thư mục gốc
```bash
npm install
```

### 2) Cài package cho backend và frontend
```bash
npm run install-all
```

### 3) Chạy cả frontend và backend
```bash
npm run dev
```

## Địa chỉ truy cập
- Frontend: `http://localhost:5173`
- Backend: `http://localhost:5000`

## Tài khoản mẫu
- Admin
  - username: `admin`
  - password: `admin123`
- Lecturer
  - username: `lecturer1`
  - password: `lecturer123`
- Student
  - username: `student1`
  - password: `student123`

## Dữ liệu mẫu có sẵn
- 2 hồ sơ sinh viên mẫu
- 3 môn học mẫu
- Dữ liệu điểm mẫu
- Lịch học mẫu

## Ghi chú
- Database SQLite sẽ tự tạo khi backend chạy lần đầu.
- Nếu muốn reset dữ liệu, xóa file `backend/school.db` rồi chạy lại backend.
- Khi bạn nâng cấp code mà muốn nạp lại dữ liệu mẫu sạch, cũng nên xóa `school.db` trước khi chạy lại.


## Bản cập nhật mới
- Sửa lỗi giảng viên tạo môn học nhưng cột **Giảng viên** hiển thị `--`.
- Từ bản này, khi giảng viên tạo hoặc sửa môn học, hệ thống sẽ tự gán đúng tên giảng viên đang đăng nhập.
- Nếu bạn đang đăng nhập sẵn trước khi cập nhật, hãy **đăng xuất rồi đăng nhập lại** để token mới có đầy đủ thông tin.


## Cập nhật mới
- Khi tạo hoặc sửa lịch học, hệ thống sẽ kiểm tra trùng giờ theo lớp và phòng học trong cùng ngày/học kỳ.
- Có thể tạo một môn/lịch học lặp lại trên nhiều ngày trong tuần trong một lần nhập.
