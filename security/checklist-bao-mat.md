# Checklist An toàn thông tin cá nhân

## 1. Password Manager (Bitwarden) – Digital Vault

- [ ] Cài Bitwarden (extension trình duyệt + ứng dụng điện thoại), tạo **Master Password** dài, dễ nhớ, chưa dùng ở đâu khác
- [ ] Dùng **Generator** để sinh mật khẩu **16–32 ký tự** (chữ hoa, chữ thường, số, ký tự đặc biệt)
- [ ] Nguyên tắc **1 tài khoản – 1 mật khẩu**: không dùng chung một mật khẩu cho nhiều tài khoản
- [ ] Chuyển toàn bộ mật khẩu cũ vào Vault và đổi các mật khẩu yếu/trùng

## 2. Xác thực 2 yếu tố (2FA / TOTP)

| Tài khoản | Phương thức 2FA | Backup Codes |
|---|---|---|
| GitHub | TOTP qua Authenticator App | Lưu vào Bitwarden |
| Email công ty | TOTP qua Authenticator App | Lưu vào Bitwarden |

- [ ] Bật 2FA cho GitHub bằng **Authenticator App** (TOTP)
- [ ] Bật 2FA cho Email công ty bằng **Authenticator App** (TOTP)
- [ ] Lưu **Backup Codes** vào Bitwarden (mục Secure Note)
- [ ] **Không chọn SMS OTP làm phương thức chính** (dễ bị chiếm SIM, chặn tin nhắn)

## 3. Nhận diện rủi ro

| Rủi ro | Mô tả | Ví dụ | Cách phòng |
|---|---|---|---|
| Phishing | Email/tin nhắn giả mạo dụ nhập mật khẩu | "Tài khoản bị khoá, bấm vào đây để xác minh" | Không bấm link lạ, tự gõ địa chỉ website |
| Typosquatting | Tên miền giả gần giống tên miền thật | `g1thub.com`, `rnicrosoft.com` | Kiểm tra kỹ tên miền; dùng Bitwarden (chỉ tự điền đúng tên miền) |
| Mã độc từ Crack | Phần mềm bẻ khoá chứa mã độc | Bản crack Office, IDE | Chỉ dùng phần mềm bản quyền/nguồn chính thức |

### Quy tắc 5 KHÔNG

1. **KHÔNG** dùng chung một mật khẩu cho nhiều tài khoản.
2. **KHÔNG** chia sẻ mật khẩu hoặc mã OTP cho bất kỳ ai, kể cả người tự xưng là IT.
3. **KHÔNG** bấm link/mở file đính kèm từ nguồn không rõ ràng.
4. **KHÔNG** cài phần mềm crack hoặc tải từ nguồn không chính thức.
5. **KHÔNG** để lộ Secrets (API Key, mật khẩu) trong mã nguồn hoặc đưa file `.env` lên GitHub.

## 4. Bảo vệ Secrets bằng `.env` và `.gitignore`

| File | Vai trò | Đưa lên GitHub? |
|---|---|---|
| `.env` | Chứa giá trị bí mật thật (ở thư mục gốc dự án) | **Không** |
| `.gitignore` | Khai báo file Git phải bỏ qua (có dòng `.env`) | Có |
| `.env.example` | Danh sách tên biến, để trống giá trị, chia sẻ cho đồng đội | Có |

- [ ] Khai báo `.env` trong `.gitignore` **trước commit đầu tiên**
- [ ] Không hardcode API Key/Password trong mã nguồn; đọc từ biến môi trường
- [ ] Cập nhật `.env.example` mỗi khi thêm biến mới (chỉ tên biến)
- [ ] Kiểm tra: `git check-ignore -v .env` phải in ra dòng khớp với `.gitignore`

Ví dụ **sai** và **đúng**:

```python
# SAI: hardcode secret trong mã nguồn
API_KEY = "sk_live_abcdef123456"

# ĐÚNG: đọc từ biến môi trường (đã nạp từ .env)
import os
API_KEY = os.getenv("API_KEY")
```

> Nếu lỡ commit secret: coi như đã lộ, **đổi (rotate) key ngay**, rồi mới xử lý lịch sử Git.
