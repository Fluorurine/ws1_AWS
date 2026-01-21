---
title: "Security Group"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

![Kiến trúc đám mây](/images/2/WS1_Step.svg?featherlight=false&width=90pc)

### Kiến trúc hoạt động như thế nào?

1. Máy khách yêu cầu URL của **phân phối CloudFront** để lấy tệp trang web cụ thể trong **thùng S3**.

2. **CloudFront** gửi yêu cầu đến **AWS WAF**. AWS WAF lọc yêu cầu bằng cách sử dụng ACL web được áp dụng cho phân phối CloudFront.

- Nếu yêu cầu được xác định là hợp lệ, luồng tiếp tục.
- Nếu yêu cầu được xác định là không hợp lệ, máy khách nhận được **lỗi 403**.

3. **CloudFront** kiểm tra bộ đệm nội bộ của nó. Nếu có khóa hợp lệ khớp với yêu cầu đến, giá trị liên quan sẽ được gửi lại cho máy khách dưới dạng phản hồi. Nếu không, luồng tiếp tục.

4. **CloudFront** chuyển tiếp yêu cầu đến URL của **Bộ cân bằng tải ứng dụng** đã chỉ định.

5. **Application Load Balancer** có một trình lắng nghe được liên kết với một nhóm mục tiêu dựa trên **hàm Lambda**. Application Load Balancer gọi hàm Lambda.

6. **Hàm Lambda** kết nối với thùng S3, thực hiện thao tác GetObject trên đó và trả về nội dung dưới dạng phản hồi.
