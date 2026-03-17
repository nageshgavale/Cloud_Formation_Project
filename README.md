# 🚀 AWS Cloud Infrastructure Project with Monitoring & Auto Scaling

## 📌 Project Overview

This project demonstrates a **highly available, scalable, and monitored cloud infrastructure** built using AWS CloudFormation.
It deploys a containerized web application using Docker on EC2 instances, with full integration of **Auto Scaling, Load Balancing, and CloudWatch monitoring**.

---

## 🏗️ Architecture

```
User → Application Load Balancer → EC2 (Auto Scaling) → Docker Container
                                      ↓
                               CloudWatch Agent
                                      ↓
                         Metrics + Logs + Alerts
                                      ↓
                                  SNS Email
```

---

## ⚙️ Services Used

* **Amazon VPC** – Custom networking (public & private subnets)
* **EC2 (Auto Scaling Group)** – Compute layer for hosting application
* **Docker** – Containerized web application
* **Application Load Balancer (ALB)** – Traffic distribution
* **Amazon RDS (MySQL)** – Managed database (private subnet)
* **Amazon S3** – Storage for backups/logs
* **AWS CloudWatch** – Monitoring & logging
* **Amazon SNS** – Email notifications
* **IAM** – Role-based access for EC2

---

## 🔥 Key Features

### ✅ High Availability

* Multi-AZ deployment using public subnets
* Load balancing via ALB

### ✅ Auto Scaling

* Automatically scales EC2 instances based on CPU utilization

### ✅ Monitoring & Alerts

* CloudWatch Agent collects:

  * CPU usage
  * Memory usage
  * Disk usage
* Docker container logs sent to CloudWatch Logs
* CloudWatch Alarms trigger SNS notifications

### ✅ Notifications

* Email alerts for:

  * High CPU usage 🚨
  * Instance launch/terminate 🔁
  * Scaling errors ❌

---

## 🐳 Docker Setup

The application runs inside a Docker container:

```bash
docker run -d -p 8090:80 kartikgavale123/kartik
```

With CloudWatch logging enabled:

```bash
--log-driver=awslogs
--log-opt awslogs-group=my-docker-logs
```

---

## 📊 CloudWatch Integration

* CloudWatch Agent installed via EC2 UserData
* Custom metrics:

  * CPU
  * Memory
  * Disk
* Log Group:

  * `my-docker-logs`

---

## 📩 SNS Alerts

SNS topic sends email notifications for:

* Auto Scaling events
* CloudWatch alarms

---

## 🚀 Deployment Steps

1. Upload `Project.yml` to AWS CloudFormation
2. Create a new stack
3. Provide required parameters:

   * Key Pair
   * Email for alerts
4. Launch stack
5. Confirm SNS email subscription
6. Access application via ALB DNS

---

## 🔐 Security

* EC2 secured using Security Groups (SSH, HTTP, App port)
* RDS deployed in private subnets
* IAM role used for CloudWatch permissions

---

## ⚠️ Improvements (Future Scope)

* Use **AWS Secrets Manager** for DB credentials
* Add **CloudWatch Dashboard**
* Enable **ALB access logs to S3**
* Integrate **CI/CD pipeline (GitHub Actions / Jenkins)**

---

## 👨‍💻 Author

**Nagesh Gavale**

* AWS | Cloud | DevOps Enthusiast
* Skills: AWS, Linux, Docker, Networking, CloudFormation

---

## ⭐ Project Highlights (For Resume)

* Designed scalable AWS architecture using CloudFormation
* Implemented real-time monitoring using CloudWatch
* Automated infrastructure provisioning (IaC)
* Integrated alerting system with SNS

---

## 📌 Conclusion

This project showcases end-to-end cloud infrastructure design with **scalability, monitoring, and automation**, making it suitable for real-world production environments.

## 🏗️ Architecture Diagram

![Architecture](architecture.png)

---
