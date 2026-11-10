# Không gian cộng tác đám mây – Phân quyền & chia sẻ

## 1. Hybrid Workflow (Local + Cloud)

- **Thao tác trên Local:** mọi file làm việc được mở và chỉnh sửa trên ổ cứng máy tính (nhanh, dùng được khi mất mạng).
- **Sao lưu tự động lên Cloud:** cài **Google Drive for Desktop**, bật **Auto Sync** cho thư mục dự án để mọi thay đổi tự động lên Cloud.
- **Data Isolation:** tài liệu công việc nằm trong tài khoản/thư mục công ty, tài liệu cá nhân nằm ở nơi khác; không trộn lẫn để tránh thất lạc và lộ dữ liệu.

## 2. Cây thư mục dự án chuẩn 5 trụ cột (kebab-case, không dấu, không khoảng trắng)

```
technova-onboarding-kit/
├── docs/                 # README.md, srs-onboarding-kit.docx
├── cloud-workspace/      # cấu trúc thư mục, bảng phân quyền
├── browser-setup/        # hồ sơ trình duyệt
├── security/             # checklist, .env.example, .gitignore
└── troubleshooting/      # mẫu bug report, cheat-sheet tìm kiếm
```

Quy ước đặt tên: chữ thường, nối bằng dấu gạch ngang (ví dụ `phan-quyen-chia-se.md`); **không** dùng `Tai Lieu Moi (1).docx`.

## 3. Bảng phân quyền chia sẻ mẫu

| Vai trò | Quyền Google Drive | Kênh giao tiếp (Lark/Slack) |
|---|---|---|
| Nhân viên mới (Owner tài liệu cá nhân) | **Editor** trên thư mục cá nhân | `#onboarding` – hỏi đáp riêng với Mentor |
| Đồng đội cùng dự án | **Editor** trên thư mục dự án chung | `#dev-<ten-du-an>` – thảo luận kỹ thuật |
| Thực tập sinh phòng ban khác | **Commenter** (chỉ góp ý) | `#thong-bao` – chỉ đọc, không chat tự do |
| Đối tác / khách mời ngoài công ty | **Viewer**, Restricted theo Email | Không cấp quyền vào Workspace nội bộ |

### Ý nghĩa 3 mức quyền

| Quyền | Được làm | Dùng khi |
|---|---|---|
| Viewer | Chỉ xem | Chia sẻ tài liệu hoàn thiện, cho đối tác |
| Commenter | Xem và nhận xét, không sửa nội dung | Xin góp ý, review |
| Editor | Sửa, thêm, xoá, chia sẻ tiếp | Đồng đội trực tiếp làm việc cùng |

### Quy tắc chia sẻ bắt buộc

- **KHÔNG BAO GIỜ** kết hợp **"Anyone with the link"** với quyền **Editor** cho bất kỳ tài liệu nào.
- Chia sẻ cho người ngoài công ty: chọn **Restricted**, thêm đúng **địa chỉ Email**, quyền **Viewer**, đặt ngày hết hạn nếu được.
- Nguyên tắc đặc quyền tối thiểu: cấp quyền thấp nhất đủ để làm việc, nâng quyền khi cần.

### Checklist kiểm tra trước khi nhấn "Share"

- [ ] Đã chọn **Restricted** (không phải Anyone with the link) cho tài liệu nội bộ
- [ ] Quyền được cấp đúng vai trò trong bảng trên
- [ ] Không có người ngoài công ty có quyền Editor
- [ ] Đã mở lại hộp thoại Share để xác nhận danh sách người truy cập

## 4. Văn hoá giao tiếp nhóm: Channel – Thread

| Kênh | Chủ đề | Quy tắc |
|---|---|---|
| `#onboarding` | Hỏi đáp nhập môn | Hỏi Mentor, mô tả rõ vấn đề |
| `#dev-<ten-du-an>` | Kỹ thuật dự án | Một chủ đề một Thread |
| `#thong-bao` | Thông báo chung | Chỉ đọc, không chat tự do |

- Mỗi chủ đề có **Channel/Topic riêng**, không trộn nhiều chủ đề vào một kênh.
- Luôn dùng **Reply in Thread** để trả lời, không gửi tin mới làm trôi tin nhắn gốc.
- **Tagging** (`@ten`) đúng người cần hành động; **không** spam `@all`/`@channel`, đặc biệt ngoài giờ làm việc.
- Tránh **No-Hello**: không nhắn "Chào anh" rồi chờ; hãy gửi luôn nội dung câu hỏi.

**Ví dụ tin nhắn đúng** (trong Thread):

> @Mentor Em đang cấu hình Google Drive for Desktop trên Windows 11, bước đăng nhập báo "Couldn't sign in". Em đã thử đăng xuất/đăng nhập lại nhưng vẫn lỗi. Anh/chị xem giúp em lỗi này, ảnh chụp đính kèm trong Thread.
