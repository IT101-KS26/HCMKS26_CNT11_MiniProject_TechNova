# TechNova Onboarding Kit

Bộ hồ sơ **Onboarding số** dành cho nhân viên mới của Startup công nghệ **TechNova**: giúp tổ chức không gian cộng tác đám mây, thiết lập trình duyệt chuyên nghiệp, bảo vệ thông tin cá nhân và tự tra cứu – gỡ lỗi trước khi nhờ IT hỗ trợ.

## Cấu trúc dự án

| Thư mục | Nội dung |
|---|---|
| `docs/` | `README.md` và tài liệu SRS `srs-onboarding-kit.docx` |
| `cloud-workspace/` | Cấu trúc thư mục, bảng phân quyền chia sẻ, quy tắc kênh giao tiếp |
| `browser-setup/` | Hồ sơ cấu hình trình duyệt (Profile, Bookmark, Extension, DevTools) |
| `security/` | Checklist bảo mật, `.env.example`, `.gitignore` |
| `troubleshooting/` | Mẫu báo cáo lỗi, cheat-sheet toán tử tìm kiếm, mẫu Prompt AI |

Tài liệu chi tiết từng module:

- [Phân quyền & chia sẻ](../cloud-workspace/phan-quyen-chia-se.md)
- [Hồ sơ trình duyệt](../browser-setup/ho-so-trinh-duyet.md)
- [Checklist bảo mật](../security/checklist-bao-mat.md)
- [Mẫu báo cáo lỗi](../troubleshooting/mau-bao-cao-loi.md)

## Hướng dẫn sử dụng

1. Tải dự án về máy và mở bằng VS Code:

```bash
git clone <duong-dan-repository>
cd TenLop_MonHoc_MiniProject_TechNova
```

2. Tạo file `.env` của riêng bạn từ file mẫu (file `.env` **không** được đưa lên GitHub):

```bash
cp security/.env.example .env
```

3. Điền giá trị thật vào `.env` trên máy của bạn, sau đó kiểm tra Git đã bỏ qua file bí mật:

```bash
git check-ignore -v .env
git status
```

## Checklist Onboarding

- [x] Dựng cây thư mục dự án theo chuẩn kebab-case
- [x] Bật Google Drive for Desktop (Auto Sync) cho thư mục làm việc
- [x] Tạo 2 Browser Profile: `Personal` và `TechNova_Work`
- [x] Sắp xếp Bookmark vào 3 thư mục `01_Work_Dev`, `02_Onboarding_Docs`, `03_Tools`
- [x] Cài Bitwarden và đổi toàn bộ mật khẩu quan trọng sang mật khẩu sinh tự động
- [x] Bật 2FA (TOTP) cho GitHub và Email công ty, lưu Backup Codes vào Bitwarden
- [x] Tạo `.env`, `.env.example`, `.gitignore` trước commit đầu tiên
- [ ] Tham gia kênh `#onboarding` và gửi tin nhắn giới thiệu cho Mentor
- [ ] Đẩy dự án lên GitHub (không gồm `.env`)

## Bảng thiết bị / tài khoản

| Thiết bị / Tài khoản | Mục đích | Bảo vệ | Trạng thái |
|---|---|---|---|
| Laptop làm việc | Lưu file Local + Auto Sync | Mã hoá ổ đĩa, khoá màn hình | Đã cấp |
| Email công ty | Liên lạc, đăng nhập công cụ | Mật khẩu 16+ ký tự, 2FA TOTP | Đã bật 2FA |
| GitHub | Quản lý mã nguồn | 2FA TOTP, Backup Codes trong Bitwarden | Đã bật 2FA |
| Google Drive | Lưu trữ và chia sẻ tài liệu | Phân quyền Viewer/Commenter/Editor | Đã cấu hình |
| Lark / Slack | Giao tiếp nhóm | Kênh theo chủ đề, Reply in Thread | Chờ tham gia |
| Bitwarden | Kho mật khẩu (Digital Vault) | Master Password mạnh, 2FA | Đã thiết lập |

---

> **Không** commit file `.env` hoặc bất kỳ API Key / mật khẩu nào lên GitHub. Chỉ chia sẻ `.env.example` (không có giá trị thật).
