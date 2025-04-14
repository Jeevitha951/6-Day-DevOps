# Day 4 – Docker Introduction & AWS EC2 Hands-on

## 📝 Summary

On the fourth day of our DevOps training, we dived deep into containerization using Docker. Alongside theory, we also carried out practical steps to launch an EC2 instance on AWS, connect via PuTTY, and install Docker on an Amazon Linux machine. This session gave us foundational knowledge of working with Docker and deploying lightweight containers on the cloud.

---

## 🚀 Launching an EC2 Instance via AWS

We started by creating a virtual server (EC2 instance) using the AWS Management Console.

### 💻 Steps to Launch EC2 and Connect with PuTTY:

- **Launch Instance:** Select *Amazon Linux 2* as the AMI.
- **Create Key Pair:** Download the `.pem` file.
- **Convert to .ppk:** Use *PuTTYgen* to convert `.pem` to `.ppk`.
- **Open PuTTY:**
  - Enter the instance’s **Public IP**.
  - Under **SSH → Auth**, browse and load the `.ppk` file.
- **Login as root:** Connect successfully to the EC2 instance.

---

## 🐳 Docker Installation on Amazon Linux

Once connected to the EC2 instance, we proceeded to install Docker:

```bash
sudo su
yum install docker -y
service docker status
service docker start
docker --version
