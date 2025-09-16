# Daily Challenge → Day 8: Linux & Virtualization

Welcome to **Day 8** of the **Daily DevOps & SRE Challenge – Season 2!** 🎉  
This day is dedicated to understanding **Linux** and **Virtualization** — the core building blocks for any DevOps or SRE engineer.

---

## 📖 Introduction
Linux is at the heart of almost every modern infrastructure.  
Virtualization allows us to run multiple systems on a single piece of hardware, making testing and scalability easy.

By completing this challenge, I strengthened my understanding of:
- Unix & Linux concepts
- Virtualization platforms and their real-world use
- Linux distribution choices for different environments
- Cloud (AWS EC2) vs Local (VirtualBox) setups

---

## 🎯 Learning Goals
- Understand the history & importance of Unix/Linux.
- Learn how virtualization powers cloud & container technologies.
- Compare RHEL, Ubuntu, Amazon Linux, and other distros.
- Practice hands-on setup of:
  - **AWS EC2** instances with different Linux OS.
  - **RHEL installation** on VirtualBox.

---

## 🚀 Steps I Followed to Create and Access an AWS EC2 Instance

1. **Logged in to AWS Management Console**  
   - Opened [https://aws.amazon.com/console](https://aws.amazon.com/console) and signed in to my account.

    a. **Opened the EC2 Dashboard**  
        - From the “Services” menu, selected **EC2**.

    b. **Launched a New Instance**  
        - Clicked **Launch instance**.

    c. **Configured Instance Details**  
        - Added a meaningful **Name** (e.g., `Myfirst`).  
        - Selected the required **Amazon Machine Image (AMI):**  
            - RHEL   
            - Ubuntu  
            - Amazon Linux 

    d. **Chose Instance Type**  
        - Picked `t2.micro` (free-tier eligible).

    e. **Created / Selected a Key Pair**  
        - Created a new key pair (`.pem` file) and downloaded it securely  
         *(used later for SSH access).*

    f. **Configured Network Settings**  
        - Used the **default VPC**.  
        - Enabled **Auto-assign Public IP**.  
        - Opened **SSH (port 22)** in the security group.

    g. **Configured Storage**  
        - Accepted the default 8 GB (or adjusted as needed).

    h. **Reviewed & Launched**  
        - Verified all settings and clicked **Launch instance**.

    i. **Connected via SSH Using MobaXterm**  
        - Opened **MobaXterm** on my local machine.  
        - Went to **Session → SSH**.  
        - Entered the instance’s **Public IP**.  
        - In the “Advanced SSH settings”, browsed and selected my downloaded key (`.pem`).  
        - Clicked **OK** to start the session and logged in as `ec2-user`.  
        - Verified the connection and started configuring the server.

2. **✅  Practical Challenge – Steps and Screenshots**  
    #### **1. RHEL 9**

* AMI: Red Hat Enterprise Linux 
* Instance Type: t3.micro
* Key Pair: `myfirst22.pem`
![Redhat](./Proof-Of-work/RHEL.png)

    #### **2. ubuntu**

* AMI: Ubuntu
* Instance Type: t3.micro
* Key Pair: `myfirst22.pem`
![Ubuntu](./Proof-Of-work/Ubuntu.png)

#### **3. Amazon Linux**

* AMI: Amazon Linux
* Instance Type: t3.micro
* Key Pair: `myfirst22.pem`
![Ubuntu](./Proof-Of-work/Amazon%20Linux.png)




**Here’s the standard command to connect to an EC2 instance via SSH 👇**

ssh -i /<pathtoyour-key.pem> ec2-user@<public-ip-address>
    -ssh → command to open an SSH session.
    -ec2-user → default username for Amazon Linux / RHEL on AWS.
    -<public-ip-address> → the Public IPv4 address of your EC2 instance.

3. **🚧 Challenges Faced**
    -I was already comfortable creating Amazon EC2 instances, so that step was easy.
    -The main challenge came when connecting to the EC2 instance: I kept seeing a            “Permission denied” error while using the .pem key.
    -The solution was to adjust the key’s permissions with:
        chmod 400 /path/to/your-key.pem

4. **💭 Final Thoughts**

This challenge reinforced how important it is to understand the basics of Linux and virtualization before diving into more advanced DevOps tools.
Learning to troubleshoot simple issues like SSH key permissions builds confidence and saves time later.

📢 Share this on social media using: #getfitwithsagar #SRELife #DevOpsForAll