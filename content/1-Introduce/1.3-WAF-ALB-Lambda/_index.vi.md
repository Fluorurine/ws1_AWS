---
title: "Internet Gateway"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3 </b> "
---

### Tường lửa ứng dụng web AWS (WAF)

![Tường lửa ứng dụng web AWS](/images/1/waf_icon.png?featherlight=false&width=10pc)

**_Amazon WAF_**, viết tắt của AWS Web Application Firewall, là **_tường lửa ứng dụng web bảo vệ ứng dụng của bạn khỏi các cuộc tấn công mạng_**. Nó cho phép bạn **_cấu hình các quy tắc tùy chỉnh_** để kiểm soát lưu lượng truy cập web dựa trên nhiều tiêu chí khác nhau, bao gồm địa chỉ IP, tiêu đề HTTP, nội dung chính, URL và bảo vệ chống lại các lỗ hổng cụ thể như SQL injection và cross-site scripting. Ngoài ra, AWS WAF cung cấp các quy tắc được xây dựng sẵn, khả năng kiểm soát bot và giám sát để củng cố thế trận bảo mật của ứng dụng của bạn.

---

### Bộ cân bằng tải ứng dụng (ALB)

![Bộ cân bằng tải ứng dụng](/images/1/alb_icon.svg?featherlight=false&width=10pc)

**_Bộ cân bằng tải ứng dụng (ALB)_** là thiết bị mạng hoạt động như **_bộ điều phối lưu lượng truy cập cho các ứng dụng của bạn_**. Nó nằm trước máy chủ web của bạn và phân phối lưu lượng truy cập đến giữa chúng.

Bộ cân bằng tải ứng dụng AWS cung cấp một số tính năng:

- **_Định tuyến thông minh_**: Định hướng lưu lượng truy cập dựa trên URL, tiêu đề hoặc các chi tiết khác.

- **_Chuyển hướng HTTPS_**: Tự động chuyển sang kết nối an toàn.
- **_Quản lý TLS_**: Xử lý mã hóa/giải mã, cải thiện hiệu suất máy chủ.
- **_Chỉ định tên máy chủ (SNI)_**: Chọn chứng chỉ SSL phù hợp dựa trên tên máy chủ của máy khách.
- **_Phiên cố định_**: Giữ cho người dùng kết nối với cùng một máy chủ bằng cách sử dụng cookie để có trải nghiệm tốt hơn.
- **_Tích hợp bảo mật_**: Hoạt động với AWS WAF để bảo vệ các ứng dụng của bạn.

---

### AWS Lambda

![Application Lambda](/images/1/lambda_icon.png?featherlight=false&width=10pc)
`**_AWS Lambda_** là **_dịch vụ điện toán không có máy chủ_**, nghĩa là bạn không phải quản lý máy chủ để chạy mã của mình. Bạn chỉ cần tải mã của mình lên và AWS Lambda sẽ lo mọi thứ khác, bao gồm cung cấp, mở rộng quy mô và quản lý cơ sở hạ tầng cơ bản.

Kiến trúc không máy chủ mang lại những lợi thế như:

- **_Hiệu quả về chi phí_**: Bạn chỉ phải trả tiền cho các tài nguyên mà mã của mình sử dụng, loại bỏ chi phí máy chủ nhàn rỗi.

- **_Khả năng mở rộng_**: Lambda có thể tự động mở rộng quy mô mã của bạn để xử lý bất kỳ lượng lưu lượng nào.
- **_Phát triển nhanh hơn_**: Tập trung vào việc viết mã mà không phải lo lắng về việc quản lý máy chủ.

**_Hàm AWS Lambda_** là một **_đoạn mã riêng lẻ chạy trên AWS Lambda_**. Bạn có thể viết hàm của mình bằng nhiều ngôn ngữ được hỗ trợ khác nhau (như Python, Node.js, Java) và xác định mục đích của hàm, chẳng hạn như xử lý dữ liệu, phản hồi các yêu cầu API hoặc kích hoạt các dịch vụ AWS khác.

Đặc điểm:

- **_Độc lập_**: Mỗi hàm là một đơn vị hoàn chỉnh với mã và logic riêng.

- **_Theo sự kiện_**: Chúng được kích hoạt bởi các sự kiện cụ thể, chẳng hạn như tải tệp lên S3 hoặc yêu cầu API Gateway.
