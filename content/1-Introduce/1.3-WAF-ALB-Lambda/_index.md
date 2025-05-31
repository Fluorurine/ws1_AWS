---
title: "WAF, Application Load Balancer & Lambda"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3 </b> "
---

### AWS Web Application Firewall (WAF)

![AWS Web Application Firewall](/images/1/waf_icon.png?featherlight=false&width=10pc)

**_Amazon WAF_**, stands for AWS Web Application Firewall, is a **_web application firewall that safeguards your applications from cyberattacks_**. It allowing you to **_configure custom rules_** that control web traffic based on various criteria, including IP addresses, HTTP headers, body content, URLs, and protection against specific vulnerabilities like SQL injection and cross-site scripting. Additionally, AWS WAF offers prebuilt rules, bot control, and monitoring capabilities to fortify your application's security posture.

---

### Application Load Balancer (ALB)

![Application Load Balancer](/images/1/alb_icon.svg?featherlight=false&width=10pc)

An **_application load balancer (ALB)_** is a network device that acts as a **_traffic director for your applications_**. It sits in front of your web servers and distributes incoming traffic among them.

An AWS application load balancer offers several features:

- **_Smart routing_**: Directs traffic based on URL, headers, or other details.

- **_HTTPS redirection_**: Makes switching to secure connections automatic.
- **_TLS management_**: Handles encryption/decryption, improving server performance.
- **_Server Name Indication (SNI)_**: Selects the appropriate SSL certificate based on the client's hostname.
- **_Sticky sessions_**: Keeps users connected to the same server by using cookies for a better experience.
- **_Security integration_**: Works with AWS WAF to protect your applications.

---

### AWS Lambda

![Application Lambda](/images/1/lambda_icon.png?featherlight=false&width=10pc)
`**_AWS Lambda_** is a **_serverless compute service_**, meaning you don't have to manage servers to run your code. You simply upload your code, and AWS Lambda takes care of everything else, including provisioning, scaling, and managing the underlying infrastructure.

Serverless architecture offers advantages like:

- **_Cost-effectiveness_**: You only pay for the resources your code uses, eliminating idle server costs.

- **_Scalability_**: Lambda can automatically scale your code to handle any amount of traffic.
- **_Faster development_**: Focus on writing code without worrying about server management.

**_AWS Lambda Function_** is an **_individual piece of code that runs on AWS Lambda_**. You can write your function in various supported languages (like Python, Node.js, Java) and define its purpose, like processing data, responding to API requests, or triggering other AWS services.

Characteristics:

- **_Self-contained_**: Each function is a complete unit with its own code and logic.

- **_Event-driven_**: They are triggered by specific events, such as a file upload to S3 or an API Gateway request.
