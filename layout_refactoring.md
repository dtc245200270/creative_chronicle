# Báo Cáo Phân Tích Refactoring Giao Diện "CreativeChronicle"

## 1. Tác hại của `position: absolute` đối với Responsive Design
Khi phần tử con áp dụng thuộc tính `position: absolute`, chúng bị tách hoàn toàn khỏi luồng tài liệu thông thường (normal document flow). Hậu quả là phần tử cha bị mất chiều cao thực tế (collapse to zero height nếu không gán cứng `height`). Khi gán cứng kích thước bằng pixel (ví dụ `height: 400px`), bố cục trở nên cứng nhắc và không thể co giãn linh hoạt theo tỷ lệ màn hình điện thoại, khiến các phần tử con đè bẹp lên nhau và che lấp các đoạn văn bản bên dưới.

## 2. Vì sao CSS Grid là giải pháp cứu cánh?
CSS Grid là hệ thống bố cục hai chiều (2D layout) mạnh mẽ, cho phép chia dòng và cột theo tỷ lệ phân đoạn linh hoạt (`fr`). Khung chứa Grid tự động tính toán kích thước thực tế dựa trên nội dung bên trong, giữ nguyên luồng hiển thị mà không làm mất chiều cao của cha. Nhờ đó, việc tạo lưới ảnh Mosaic bất đối xứng (ảnh chính chiếm `span 2` hàng, ảnh phụ xếp cạnh) trở nên tự nhiên, kết hợp media query chuyển về 1 cột trên mobile một cách mượt mà và triệt tiêu hoàn toàn rủi ro vỡ giao diện.
