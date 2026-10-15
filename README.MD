# IT108 - Session 09 - Bài1: xử lý xung đột tài liệu trên GitHub

## 1. Phần 1: Phân tích tình huống và sai lầm của Nam

### 1.1. Chỉ ra 2 sai lầm trong tư duy của Nam
- **Sai lầm về định dạng tệp và khả năng hiển thị:** Nam cho rằng dùng Microsoft Word (`.docx`) là tối ưu nhờ có giao diện đồ họa trực quan. Tuy nhiên, GitHub là nền tảng quản lý mã nguồn sinh ra để xử lý các tài liệu văn bản thô. File Word là định dạng nhị phân đóng kín, khiến GitHub **không thể render (hiển thị nội dung)** trực tiếp trên trình duyệt web, bắt buộc các thành viên khác phải tải về máy mới xem được.
- **Sai lầm về quản lý phiên bản và xung đột (Git Conflict):** Nam nghĩ dùng Word tiện lợi cho việc trình bày, nhưng trên hệ thống Git, mỗi khi Nam sửa dù chỉ một dấu phẩy, toàn bộ file `.docx` sẽ bị coi là một khối nhị phân thay đổi. Điều này dẫn đến **xung đột toàn bộ tệp (Conflict)** và hệ thống không thể tự động ghép nối (merge) code được.

### 1.2. Ưu điểm vượt trội của Markdown và khả năng chống lỗi
- **Dạng văn bản thô (Plain Text):** Markdown lưu trữ nội dung dưới dạng chữ viết thuần túy, dung lượng nhẹ và được GitHub hỗ trợ hiển thị trực tiếp ngay trên giao diện web.
- **Khả năng chống hư hại dữ liệu (Bẫy dữ liệu):** 
  - *Đối với Word:* Nếu tệp Word bị lỗi truyền tải mạng làm mất đúng 1 byte dữ liệu, cấu trúc ngầm bên trong (định dạng nén zip/XML) sẽ bị phá vỡ hoàn toàn và file sẽ hỏng không thể mở được.
  - *Đối với Markdown:* Do là văn bản thô, nếu một vài dòng hoặc byte bị lỗi hay thất lạc, các phần còn lại của tài liệu vẫn đọc và khôi phục nội dung bình thường mà không làm sập toàn bộ cấu trúc file.
- **Hỗ trợ Git Diff tối ưu:** Giúp hệ thống so sánh chi tiết từng dòng (line-by-line) để biết ai đã thay đổi nội dung gì, giảm thiểu tối đa tình trạng xung đột mã nguồn khi làm việc nhóm.

---

## 2. Phần 2: Nội dung chuyển đổi sang Markdown

```markdown
# Giới thiệu Dự án Quản lý Sách

Dự án Website bán sách trực tuyến giúp người dùng tìm kiếm, thêm vào giỏ hàng và thanh toán nhanh chóng, an toàn.

## Tính năng chính
- Tìm kiếm sách theo tên, tác giả.
- Thêm vào giỏ hàng linh hoạt.
- Thanh toán trực tuyến dễ dàng.