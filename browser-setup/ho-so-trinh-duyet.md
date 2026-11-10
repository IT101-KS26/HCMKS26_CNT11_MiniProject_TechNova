# Hồ sơ cấu hình Trình duyệt chuyên nghiệp

## 1. Đa Browser Profile (Data Isolation)

| Profile | Mục đích | Đăng nhập bằng |
|---|---|---|
| `Personal` | Việc cá nhân (mạng xã hội, mua sắm, giải trí) | Tài khoản Google cá nhân |
| `TechNova_Work` | Công việc TechNova (Drive, Lark/Slack, GitHub công ty) | Email công ty |

- Mỗi Profile có **Cookies, Session, Bookmark, Extension, lịch sử riêng** → không lẫn đăng nhập, giảm rủi ro lộ dữ liệu.
- **Không** dùng chung một Profile cho việc cá nhân và công việc.
- Cách tạo (Chrome): ảnh đại diện góc phải → **Add profile** → đặt tên → bật **Sync** theo tài khoản tương ứng. Đặt màu/chủ đề khác nhau để nhận biết nhanh.

## 2. Bookmark Manager (3 thư mục)

| Thư mục | Nội dung gợi ý |
|---|---|
| `01_Work_Dev` | GitHub, VS Code for the Web, Google Drive công ty, Lark/Slack |
| `02_Onboarding_Docs` | README dự án, SRS, bảng phân quyền, hướng dẫn nội bộ |
| `03_Tools` | Bitwarden, Google Search operators, StackOverflow, MDN Web Docs |

Quy tắc: đặt tên bookmark ngắn gọn, không để bookmark rời ngoài thư mục; rà soát và xoá link chết mỗi tháng.

## 3. Extension theo 3 nhóm

| Nhóm | Extension ví dụ | Công dụng |
|---|---|---|
| Dev Suite | JSON Formatter, Wappalyzer, Web Developer | Đọc JSON, nhận diện công nghệ website, kiểm tra trang |
| Productivity Suite | OneTab, Notion Web Clipper, Loom | Gom tab, lưu nội dung, quay màn hình báo lỗi |
| Security Suite | Bitwarden, uBlock Origin, Privacy Badger | Quản lý mật khẩu, chặn quảng cáo/theo dõi |

**Giới hạn quyền Site Access = On click:** vào `chrome://extensions` → chọn **Details** của từng extension → mục **Site access** → chọn **On click**. Extension chỉ đọc nội dung trang khi bạn chủ động bấm vào nó.

> Chỉ cài extension từ Chrome Web Store, kiểm tra số người dùng, đánh giá và quyền yêu cầu trước khi cài; gỡ extension không dùng.

## 4. Thực hành DevTools (F12)

| Thao tác | Cách làm | Mục đích |
|---|---|---|
| Inspect Element | Chuột phải → **Inspect** (hoặc F12 → mũi tên chọn phần tử) | Xem/sửa tạm HTML, CSS, kiểm tra giao diện |
| Tab Network | F12 → **Network** → F5 | Tìm request lỗi (màu đỏ), xem mã 404/500 |
| Tab Console | F12 → **Console** | Đọc thông báo lỗi JavaScript |
| Hard Reload | **Ctrl + Shift + R** (Windows) / **Cmd + Shift + R** (macOS) | Tải lại, bỏ qua Cache để thấy bản mã mới nhất |

### Phân biệt Cache và Cookies

| | Cache | Cookies |
|---|---|---|
| Lưu gì | Bản sao file tĩnh (ảnh, CSS, JS) | Dữ liệu nhỏ: phiên đăng nhập, tuỳ chọn |
| Mục đích | Tải trang nhanh hơn | Ghi nhớ người dùng/phiên làm việc |
| Xoá thì | Trang tải lại chậm hơn lần đầu | Bị đăng xuất khỏi các website |
| Khi nào xoá | Giao diện hiển thị bản cũ | Lỗi đăng nhập, phiên hỏng |

**Quy tắc:** luôn **Hard Reload** trước khi kết luận giao diện bị lỗi, vì trình duyệt có thể đang hiển thị bản đã lưu trong Cache.
