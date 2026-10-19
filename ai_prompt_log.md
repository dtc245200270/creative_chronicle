# Nhật Ký Tương Tác AI (AI Prompt Log)

## Prompt 1: Tìm hiểu CSS Grid Mosaic Layout
- **Prompt:** "Làm thế nào để dựng một Mosaic Gallery gồm 1 ảnh lớn bên trái và 2 ảnh nhỏ xếp chồng bên phải bằng CSS Grid mà không dùng absolute?"
- **AI Solution:** Áp dụng `display: grid; grid-template-columns: 2fr 1fr;` kết hợp `grid-row: 1 / 3` (hoặc `grid-row: span 2`) cho ảnh chính. Khi trên mobile (max-width: 768px), chỉ cần chuyển `grid-template-columns: 1fr` và trả `grid-row: auto` là ảnh tự động xếp chồng dạng cột dọc.

## Prompt 2: Tối ưu khoảng cách và Flexbox bằng Bootstrap Spacing Utilities
- **Prompt:** "Làm sao căn giữa theo chiều dọc Avatar, tên tác giả và nút Share trên cùng một hàng bằng Bootstrap 5 mà không cần viết CSS ngoài?"
- **AI Solution:** Dùng utility class `d-flex align-items-center justify-content-between flex-wrap gap-3`. Bọc nhóm Avatar + thông tin bằng `d-flex align-items-center gap-3`, nhóm Share button bằng `d-flex gap-2`. Khi màn hình quá hẹp, `flex-wrap` sẽ đẩy cụm nút bấm xuống dưới ngay ngắn.

## Prompt 3: Chia lưới bài viết đề xuất bằng Bootstrap Grid Breakpoints
- **Prompt:** "Làm thế nào để chia 4 bài viết đề xuất thành 4 cột trên Desktop (lg), 2 cột trên Tablet (md), và 1 cột trên Mobile (xs/sm)?"
- **AI Solution:** Bọc danh sách trong `<div class="row g-4">`, mỗi thẻ con áp dụng các class `<div class="col-12 col-md-6 col-lg-3">`.
