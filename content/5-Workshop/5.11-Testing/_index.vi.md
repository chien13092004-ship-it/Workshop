---
title : "Truy cập S3 từ môi trường on-premises"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.11. </b> "
---

# 5.11. Kiểm thử

Phần này trình bày quá trình triển khai hoàn chỉnh nền tảng thương mại điện tử TechMarket trên AWS. Nội dung giới thiệu các giao diện chính của ứng dụng và giải thích cách từng chức năng tương tác với hạ tầng đám mây đã triển khai, bao gồm Amazon ECS Fargate, Amazon S3, MongoDB Atlas, Amazon Route 53, AWS Certificate Manager (ACM), Application Load Balancer, Amazon CloudWatch, Amazon ECR và AWS CodeBuild.

---

# 1. Website Khách hàng

## A. Trang chủ

Trang chủ là giao diện chính nơi khách hàng duyệt các sản phẩm có trên nền tảng TechMarket.

### Tích hợp hạ tầng

Ứng dụng Node.js Express được triển khai trên Amazon ECS Fargate và được công khai thông qua Application Load Balancer. Route 53 phân giải tên miền tùy chỉnh trong khi ACM cung cấp mã hóa HTTPS. Thông tin sản phẩm được lấy từ MongoDB Atlas và hình ảnh sản phẩm được tải từ Amazon S3.

### Luồng dữ liệu

Khách hàng truy cập **https://techmarketstore.store**

↓

Route 53 phân giải tên miền.

↓

Application Load Balancer chuyển tiếp yêu cầu.

↓

Amazon ECS xử lý yêu cầu.

↓

MongoDB Atlas trả về thông tin sản phẩm.

↓

Amazon S3 trả về hình ảnh sản phẩm.

↓

Trang chủ được hiển thị.

<br>

![Homepage](/images/5-Workshop/5.11-Testing/homepage.png)

---

## B. Đăng ký người dùng

Khách hàng có thể đăng ký tài khoản mới trước khi sử dụng các chức năng mua sắm.

### Tích hợp hạ tầng

Các yêu cầu đăng ký được xử lý bởi ứng dụng Express chạy trên Amazon ECS. Thông tin người dùng được xác thực trước khi lưu vào MongoDB Atlas. Mật khẩu được mã hóa trước khi lưu trữ.

![Register Type](/images/5-Workshop/5.11-Testing/register-type.jpg)

![Customer Register](/images/5-Workshop/5.11-Testing/customer-register.jpg)

---

## C. Đăng ký cửa hàng

Khách hàng có thể đăng ký cửa hàng trực tuyến của riêng mình và trở thành người bán trên nền tảng.

### Tích hợp hạ tầng

Các yêu cầu đăng ký cửa hàng được gửi đến backend Node.js chạy trên Amazon ECS. Thông tin cửa hàng được lưu vào MongoDB Atlas và chờ quản trị viên phê duyệt.

![Shop Register](/images/5-Workshop/5.11-Testing/shop-register.jpg)

---

## D. Đăng nhập

Người dùng xác thực bằng email và mật khẩu trước khi truy cập các tài nguyên được bảo vệ.

### Tích hợp hạ tầng

Quá trình xác thực được xử lý hoàn toàn bởi ứng dụng Express triển khai trên Amazon ECS. Thông tin đăng nhập của người dùng được xác minh với MongoDB Atlas và các phiên đăng nhập được quản lý bằng Express Session.

![Login](/images/5-Workshop/5.11-Testing/login.jpg)

---

## E. Hồ sơ người dùng

Trang hồ sơ cho phép khách hàng cập nhật thông tin cá nhân và tải lên ảnh đại diện.

### Tích hợp hạ tầng

Thông tin hồ sơ được lấy từ MongoDB Atlas. Ảnh đại diện được tải lên Amazon S3, trong khi URL của ảnh được lưu trong MongoDB Atlas.

![Profile](/images/5-Workshop/5.11-Testing/profile.jpg)

---

## F. Chi tiết sản phẩm

Trang chi tiết sản phẩm hiển thị thông số kỹ thuật, mô tả, giá bán, tình trạng tồn kho và các tùy chọn mua hàng.

### Tích hợp hạ tầng

Thông tin sản phẩm được lấy từ MongoDB Atlas trong khi hình ảnh sản phẩm được phục vụ trực tiếp từ Amazon S3. Toàn bộ logic nghiệp vụ được xử lý bởi ứng dụng Node.js chạy trên Amazon ECS.

![Product Detail](/images/5-Workshop/5.11-Testing/product-detail.jpg)

---

## G. Thanh toán

Khách hàng có thể xem lại thông tin đơn hàng trước khi hoàn tất việc mua.

### Tích hợp hạ tầng

Các yêu cầu thanh toán được xử lý bởi backend Express triển khai trên Amazon ECS. Thông tin đơn hàng được xác thực trước khi lưu vào MongoDB Atlas.

![Checkout](/images/5-Workshop/5.11-Testing/checkout.jpg)

---

## H. Trang thanh toán

Trang thanh toán cho phép khách hàng xem lại thông tin đơn hàng, thông tin khách hàng, phương thức thanh toán và xác nhận đơn hàng.

### Tích hợp hạ tầng

Yêu cầu thanh toán được xử lý bởi ứng dụng Node.js Express chạy trên Amazon ECS. Chi tiết đơn hàng được lấy từ MongoDB Atlas trước khi xử lý xác nhận thanh toán.

![Payment Page](/images/5-Workshop/5.11-Testing/payment-page.jpg)

---

## I. Đặt hàng thành công

Sau khi xác nhận thanh toán, khách hàng nhận được thông báo đặt hàng thành công.

### Tích hợp hạ tầng

Ứng dụng ghi nhận đơn hàng đã hoàn tất vào MongoDB Atlas trước khi trả về trang xác nhận.

![Order Success](/images/5-Workshop/5.11-Testing/order-success.jpg)

---

# 2. Quản lý cửa hàng

## A. Bảng điều khiển cửa hàng

Chủ cửa hàng quản lý sản phẩm, theo dõi đơn hàng của khách hàng và xem thống kê kinh doanh.

### Tích hợp hạ tầng

Tất cả các thao tác quản lý được thực hiện bởi backend Node.js chạy trên Amazon ECS. Dữ liệu kinh doanh được lưu trong MongoDB Atlas trong khi hình ảnh sản phẩm đã tải lên được lưu trên Amazon S3.

![Shop Dashboard](/images/5-Workshop/5.11-Testing/shop-dashboard.jpg)

---

## B. Quản lý đơn hàng

Chủ cửa hàng quản lý đơn hàng của khách hàng, cập nhật trạng thái đơn hàng và xử lý các giao dịch đã hoàn tất.

### Tích hợp hạ tầng

Thông tin đơn hàng được lấy từ MongoDB Atlas. Các cập nhật trạng thái được xử lý bởi ứng dụng ECS và được đồng bộ ngay lập tức với cơ sở dữ liệu.

![Order Management](/images/5-Workshop/5.11-Testing/shop-orders.jpg)

---

## C. Thống kê hoa hồng

Chủ cửa hàng có thể theo dõi doanh thu và hoa hồng được tạo từ các đơn hàng đã hoàn tất.

### Tích hợp hạ tầng

Báo cáo doanh thu được tính toán động bởi backend sử dụng dữ liệu lưu trong MongoDB Atlas. Kết quả được trình bày trên bảng điều khiển thống kê.

![Commission Report](/images/5-Workshop/5.11-Testing/commission-report.jpg)

---

# 3. Bảng điều khiển quản trị viên

## A. Bảng điều khiển quản trị viên

Quản trị viên có thể theo dõi người dùng, cửa hàng và thống kê tổng quan của nền tảng.

### Tích hợp hạ tầng

Bảng điều khiển quản trị tổng hợp thông tin trực tiếp từ MongoDB Atlas thông qua ứng dụng Express chạy trên Amazon ECS.

Thông tin hiển thị bao gồm:

- Tổng số người dùng
- Tổng số cửa hàng
- Trạng thái cửa hàng
- Thông tin người dùng

![Admin Dashboard](/images/5-Workshop/5.11-Testing/admin-dashboard.jpg)

---

## B. Quản lý đơn hàng của quản trị viên

Quản trị viên quản lý đơn hàng của khách hàng, theo dõi trạng thái đơn hàng và cập nhật thông tin xử lý.

### Tích hợp hạ tầng

Thông tin đơn hàng được lấy từ MongoDB Atlas thông qua backend Node.js triển khai trên Amazon ECS. Tất cả các cập nhật trạng thái đơn hàng được đồng bộ với cơ sở dữ liệu ngay sau khi thực hiện.

![Admin Order Management](/images/5-Workshop/5.11-Testing/admin-order-management.jpg)

---

## C. Quản lý người dùng

Quản trị viên quản lý tài khoản khách hàng và theo dõi người dùng đã đăng ký.

### Tích hợp hạ tầng

Thông tin người dùng được truy vấn từ MongoDB Atlas. Các thao tác quản trị được thực hiện bởi ứng dụng ECS.

![User Management](/images/5-Workshop/5.11-Testing/admin-users.jpg)

---

## D. Quản lý cửa hàng

Quản trị viên phê duyệt hoặc từ chối các yêu cầu đăng ký cửa hàng.

### Tích hợp hạ tầng

Thông tin cửa hàng được lấy từ MongoDB Atlas và các quyết định phê duyệt được xử lý thông qua ứng dụng backend.

![Shop Management](/images/5-Workshop/5.11-Testing/admin-shops.jpg)

---

## E. Báo cáo

Quản trị viên có thể xem báo cáo doanh thu và thống kê hoa hồng trên toàn bộ nền tảng.

### Tích hợp hạ tầng

Mô-đun báo cáo tổng hợp thông tin bán hàng từ MongoDB Atlas. Các phép tính được thực hiện bởi backend Node.js và hiển thị thông qua giao diện quản trị viên.

![Reports](/images/5-Workshop/5.11-Testing/admin-reports.jpg)

---

## F. Thống kê hoa hồng

Quản trị viên có thể xem hoa hồng toàn nền tảng, doanh thu theo tháng, các đơn hàng đã hoàn tất và trạng thái thanh toán của các bản ghi hoa hồng.

### Tích hợp hạ tầng

Backend Node.js tổng hợp dữ liệu hoa hồng từ MongoDB Atlas và trả về các bản tóm tắt thống kê cho bảng điều khiển quản trị viên. Các phép tính được tạo động dựa trên các đơn hàng đã hoàn tất.

![Admin Commission Report](/images/5-Workshop/5.11-Testing/commission-report.jpg)

---

# Các dịch vụ AWS được minh họa

Trong quá trình kiểm thử ứng dụng, nền tảng đã triển khai tích hợp các dịch vụ AWS sau:

| Dịch vụ AWS | Mục đích |
|------------|----------|
| Amazon ECS Fargate | Lưu trữ ứng dụng Node.js Express |
| Amazon ECR | Lưu trữ hình ảnh Docker container |
| Amazon S3 | Lưu trữ hình ảnh sản phẩm và ảnh đại diện người dùng |
| MongoDB Atlas | Lưu trữ dữ liệu ứng dụng |
| Amazon Route 53 | Cung cấp phân giải tên miền |
| AWS Certificate Manager | Cung cấp mã hóa HTTPS |
| Application Load Balancer | Phân phối lưu lượng truy cập đến |
| Amazon CloudWatch | Giám sát tình trạng ứng dụng |
| AWS CodeBuild | Tự động hóa quá trình build và triển khai |

Việc thực thi thành công tất cả các giao diện chứng minh rằng ứng dụng TechMarket đã được triển khai hoàn chỉnh và đang hoạt động chính xác trên hạ tầng AWS Cloud.