---
title: "Giới thiệu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

Kiến trúc này lấy cảm hứng từ [Hướng dẫn theo quy định của AWS](https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/serve-static-content-in-an-amazon-s3-bucket-through-a-vpc-by-using-amazon-cloudfront.html) lý tưởng.

Khi bạn phục vụ nội dung tĩnh được lưu trữ trên **Amazon Web Services (AWS)**, phương pháp được khuyến nghị là sử dụng thùng **Amazon Simple Storage Service (S3)** làm nguồn gốc và sử dụng Amazon CloudFront để phân phối nội dung. Giải pháp này có hai lợi ích chính. Trước hết là sự tiện lợi của việc lưu trữ đệm nội dung tĩnh tại các vị trí biên. Lý do thứ hai là bạn có thể xác định danh sách kiểm soát truy cập web (web ACL) cho bản phân phối **CloudFront**, giúp bạn bảo mật các yêu cầu đối với nội dung với chi phí cấu hình và quản trị tối thiểu.

Tuy nhiên, **có một hạn chế chung về kiến ​​trúc đối với phương pháp tiêu chuẩn được khuyến nghị**. Trong một số môi trường, bạn muốn các thiết bị tường lửa ảo được triển khai trong một đám mây riêng ảo (VPC) để kiểm tra tất cả nội dung, bao gồm cả nội dung tĩnh. Phương pháp tiếp cận tiêu chuẩn không định tuyến lưu lượng qua VPC để kiểm tra. Mẫu này cung cấp một giải pháp kiến ​​trúc thay thế. Bạn vẫn sử dụng bản phân phối CloudFront để phục vụ nội dung tĩnh trong thùng S3, nhưng lưu lượng được định tuyến qua VPC bằng cách sử dụng Bộ cân bằng tải ứng dụng. Sau đó, một hàm AWS Lambda sẽ truy xuất và trả về nội dung từ thùng S3.

![Phục vụ nội dung tĩnh qua VPC với CloudFront](/images/1/WS1.svg?featherlight=false&width=90pc "Phục vụ nội dung tĩnh qua VPC với CloudFront")

#### Nội dung

- [Subnets](1.1-subnets/)
- [Route Table](1.2-routetable/)
- [Internet Gateway](1.3-internetgateway/)
- [NAT Gateway](1.4-natgateway/)

Bây giờ chúng ta sẽ cùng nhau đi qua các khái niệm cơ bản nhất của VPC nhé.
