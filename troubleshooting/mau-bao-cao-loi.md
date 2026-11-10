# Bộ kỹ năng Tự tra cứu & Gỡ lỗi

## 1. Mẫu báo cáo lỗi (Bug Reporting Framework 4 bước)

| Phần | Nội dung cần ghi |
|---|---|
| **Context** | Đang làm gì, trên thiết bị/phần mềm/phiên bản nào |
| **Expected** | Kết quả mong đợi |
| **Actual** | Điều thực sự xảy ra |
| **Log / Screenshot** | Thông báo lỗi **nguyên văn** hoặc ảnh chụp màn hình |

**Mẫu để điền:**

```
[Bug Report] <tiêu đề ngắn>
- Context:
- Expected:
- Actual:
- Log/Screenshot:
```

**Ví dụ đã điền:**

```
[Bug Report] Không đăng nhập được Google Drive for Desktop
- Context: Laptop Windows 11, Google Drive for Desktop 90.0, đăng nhập bằng email công ty, mạng Wi-Fi văn phòng.
- Expected: Đăng nhập thành công và thư mục Drive hiện trong File Explorer.
- Actual: Hiện cửa sổ đăng nhập rồi báo lỗi; đã thử đăng xuất/đăng nhập lại và khởi động lại máy nhưng vẫn lỗi.
- Log/Screenshot: "Couldn't sign in. Check your internet connection and try again." (ảnh chụp đính kèm)
```

**Báo lỗi sai (tránh):** *"Bị lỗi rồi giúp em với"* – thiếu Context và Log nên sẽ bị hỏi lại nhiều lần, mất thời gian cho cả hai bên.

## 2. Cheat-sheet toán tử tìm kiếm Google

| Toán tử | Công dụng | Ví dụ |
|---|---|---|
| `site:` | Giới hạn tìm trong một website | `site:stackoverflow.com git push rejected` |
| `" "` | Khớp chính xác cụm từ/thông báo lỗi | `"Permission denied (publickey)"` |
| `-` | Loại trừ từ khoá | `python error -django` |

**Kết hợp:**

```
site:stackoverflow.com "fatal: not a git repository" -svn
```

**Sai:** gõ nguyên câu văn nói như *"em bị lỗi git không push được thì phải làm sao ạ"*. **Đúng:** từ khoá ngắn + thông báo lỗi nguyên văn trong ngoặc kép.

## 3. Đọc StackOverflow

- Ưu tiên câu trả lời có dấu tích xanh **Accepted Answer** và số **Upvote cao**.
- Kiểm tra **ngày đăng**: bài đăng quá **5 năm** có thể đã lỗi thời vì phiên bản phần mềm thay đổi; xem các câu trả lời/bình luận mới hơn.
- Đối chiếu phiên bản (OS, ngôn ngữ, thư viện) của bạn với phiên bản trong câu hỏi.

## 4. Đọc GitHub Issues

- Xem trạng thái **Open** (chưa xử lý) hay **Closed** (đã đóng, thường kèm bản sửa).
- Tìm bình luận có chữ **workaround** để có cách xử lý tạm thời.
- Tìm Issue trùng lỗi trước khi tạo Issue mới; khi tạo mới, dùng khung Bug Report ở trên.

## 5. Prompt AI 3 thành phần (Ngữ cảnh – Lỗi nguyên văn – Yêu cầu)

```
[Ngữ cảnh] Tôi là thực tập sinh, đang dùng Windows 11, Git 2.45, chạy lệnh git push origin main.
[Lỗi nguyên văn] "fatal: not a git repository (or any of the parent directories): .git"
[Yêu cầu] Dịch lỗi sang tiếng Việt, giải thích nguyên nhân và đưa ra các bước sửa từng bước, giải thích ngắn gọn cho người mới.
```

> Không đưa mật khẩu, API Key, dữ liệu nội bộ vào Prompt gửi AI.

## 6. Quy trình tự xử lý sự cố

1. Đọc kỹ thông báo lỗi và ghi lại **nguyên văn**.
2. Tra cứu Google bằng `site:`, `" "`, `-`.
3. Đọc StackOverflow / GitHub Issues đúng cách; nhờ AI giải thích bằng Prompt 3 thành phần.
4. Nếu vẫn chưa xử lý được: gửi **Bug Report** đủ 4 phần vào kênh hỗ trợ (Reply in Thread, tag đúng người).
