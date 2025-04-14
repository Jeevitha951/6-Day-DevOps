# Day 3 – Exploring AWS IAM, EC2, CI/CD Pipeline, and Docker Setup

### AWS IAM: Managing User Access

In this session, we dove into **AWS IAM (Identity and Access Management)**, which is essential for controlling access to AWS services and resources. IAM helps you securely manage who can access what in your AWS environment.

**Steps to Set Up an IAM User:**
1. Access the IAM section in the AWS Console.
2. Go to **Access Management > Users** and click **Create User**.
3. Assign a user name, select **AWS Management Console access**, and set the password.
4. Attach the **AdministratorAccess** policy to the user.
5. Complete the setup, noting down the sign-in URL, username, and password for the IAM user.

After the IAM user is created, they can log into the AWS Management Console using their credentials.

---

### AWS EC2: Launching a Linux Instance

The next step involved launching an **EC2 instance** on AWS to work with cloud-based virtual machines.

**Steps to Launch an EC2 Instance:**
1. Go to the EC2 dashboard in the AWS Console and click **Launch Instance**.
2. Select **Amazon Linux AMI** and choose an appropriate instance type (e.g., `t2.micro` for Free Tier).
3. Configure the instance settings, add storage, and adjust the security group settings to allow **SSH (port 22)** and optionally **HTTP (port 80)**.
4. Create and download the key pair (.pem file) to access the instance securely.

---

### Accessing EC2 Using PuTTY

We then learned how to access the EC2 instance via SSH using **PuTTY** (a popular SSH client for Windows).

**Steps to Configure PuTTY:**
1. Convert the downloaded `.pem` file into the `.ppk` format using **PuTTYgen**.
2. Open **PuTTY**, enter the instance's **Public IP** under **Host Name**, and configure the session to use the `.ppk` file for authentication.
3. Once connected to the instance, run the following command to update the system:

    ```bash
    sudo yum update -y
    ```

---

### Setting Up Docker on EC2

We continued by installing **Docker** on our EC2 instance, which is essential for containerizing applications in DevOps.

**Steps to Install Docker:**
1. Run the following commands on the EC2 instance:

    ```bash
    sudo yum install -y docker
    sudo systemctl start docker
    sudo systemctl enable docker
    ```

2. Verify Docker installation by checking its version:

    ```bash
    docker --version
    ```

If the version is displayed, Docker has been successfully installed.

---

### CI/CD Pipeline: Concept & Hands-On Practice

We were introduced to the concept of **CI/CD (Continuous Integration/Continuous Deployment)** and how it automates the process of building, testing, and deploying code changes.

A simple CI/CD pipeline workflow was demonstrated, involving:
- **IAM User Creation**  
- **Launching EC2 Instance**  
- **Configuring CI Pipeline**  
- **Setting Up Docker**  
- **Deploying the Application**

We also got hands-on with deploying a basic **HTML/NodeJS app** using a Docker container.

---

### Docker Commands and Configuration

We worked with Docker commands to build and run containers, as well as create a **Dockerfile** to containerize a web app.

**Example Docker Commands:**
1. Navigate to the directory of the app:

    ```bash
    cd Calculator_using_htmlcssjs
    ```

2. Build the Docker image:

    ```bash
    docker build -t my-app .
    ```

3. Run the container in detached mode, mapping port 80:

    ```bash
    docker run -d -p 80:80 my-app
    ```

---

### Creating a Dockerfile

Here’s an example of a **Dockerfile** to containerize a simple static website:

```Dockerfile
# Use BusyBox image with HTTP server
FROM busybox:latest

# Set the working directory inside the container
WORKDIR /www

# Copy the website files to the container
COPY . /www

# Expose port 80 for HTTP traffic
EXPOSE 80

# Run the HTTP server
CMD ["httpd", "-f", "-v", "-p", "80"]

