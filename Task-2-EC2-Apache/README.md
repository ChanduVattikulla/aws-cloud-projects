# ☁️ Deploy a Web Server on AWS EC2

> Provisioning an Ubuntu virtual machine, configuring secure access, and deploying a web server with Apache.

<p align="center">

![AWS](https://img.shields.io/badge/AWS-EC2-FF9900?logo=amazonaws\&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-E95420?logo=ubuntu\&logoColor=white)
![Apache](https://img.shields.io/badge/Apache2-Web_Server-D22128?logo=apache\&logoColor=white)
![Free Tier](https://img.shields.io/badge/AWS-Free_Tier-success)

</p>

---

## 📖 Overview

Unlike static website hosting on S3, this project explores the **compute** side of AWS by deploying a Linux virtual machine, configuring networking, installing Apache, and serving a custom webpage over the internet.

---

## 🏗️ Architecture

```mermaid
flowchart LR
    A[Internet] --> B[Public IP]
    B --> C[Security Group]
    C -->|SSH 22| D[Ubuntu EC2]
    C -->|HTTP 80| D
    D --> E[Apache2]
    E --> F[Custom Website]
```

---

## 🚀 Deployment Journey

```mermaid
flowchart LR
    A[Launch EC2]
    --> B[Configure Security Group]
    --> C[SSH Access]
    --> D[Install Apache]
    --> E[Verify Default Page]
    --> F[Deploy Custom Page]
    --> G[Completed]
```

---

## ⚙️ AWS Configuration

| Component  | Value                         |
| ---------- | ----------------------------- |
| Service    | Amazon EC2                    |
| OS         | Ubuntu 24.04 LTS              |
| Instance   | t3.micro (Free Tier Eligible) |
| Web Server | Apache2                       |
| Storage    | 8 GiB gp3                     |
| SSH        | Port 22                       |
| HTTP       | Port 80                       |

---

## 🧩 What Happened

```text
☁️ Launched an Ubuntu EC2 instance
        │
        ▼
🔒 Configured Security Group
        │
        ▼
💻 Connected via SSH
        │
        ▼
📦 Installed Apache2
        │
        ▼
🌐 Verified Apache Default Page
        │
        ▼
✨ Replaced it with
   "Hello from Cloud VM"
```

---

## 💻 Commands Used

```bash
sudo apt update
sudo apt upgrade -y
sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2
sudo systemctl status apache2
echo "<h1>Hello from Cloud VM</h1>" | sudo tee /var/www/html/index.html
```

---

## 📸 Screenshots

```
images/
├── ec2-dashboard.png
├── security-group.png
├── ssh-terminal.png
├── apache-status.png
├── apache-default-page.png
└── hello-from-cloud-vm.png
```

---

## 🛠 Services Used

| AWS Service    | Purpose               |
| -------------- | --------------------- |
| EC2            | Virtual Machine       |
| Security Group | Firewall              |
| EBS            | Root Storage          |
| VPC            | Networking            |
| SSH            | Remote Administration |
| Apache2        | Web Server            |

---

## 💡 Challenges

| Challenge                                          | Solution                                                        |
| -------------------------------------------------- | --------------------------------------------------------------- |
| Free Tier offered `t3.micro` instead of `t2.micro` | Used the current Free Tier eligible instance                    |
| Needed to verify networking                        | Confirmed the default Apache page before customization          |
| Wanted to save Free Tier hours                     | Collected screenshots and stopped the instance after completion |

---

## 📚 Key Learnings

* Provisioning cloud virtual machines
* Connecting securely with SSH
* Configuring Security Groups
* Installing and managing Apache
* Serving a website from Linux
* Verifying deployments before customization
* Managing AWS resources responsibly

---

## ✅ Final Outcome

* ✔ Ubuntu EC2 instance deployed
* ✔ Apache2 installed and running
* ✔ HTTP access configured
* ✔ Custom **Hello from Cloud VM** webpage deployed
* ✔ Successfully completed within AWS Free Tier

---

## 📷 Final Result

```text
Internet
   │
Public IP
   │
Ubuntu EC2
   │
Apache2
   │
Hello from Cloud VM 🚀
```

---

<div align="center">

**Built with ❤️ using AWS EC2, Ubuntu & Apache**

⭐ *If you found this project interesting, consider giving it a star.*

</div>
