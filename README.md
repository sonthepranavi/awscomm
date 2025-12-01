AWS
# ✅ **Exercise 1: Deploy index.html on EC2 using Docker (Clean, Correct Steps)**

### **Step 1: Login to AWS Academy**

* Open course email → click **Start**
* Choose **Student Login** → enter credentials
* Go to **Modules** → select **Launch AWS Academy Lab**
* Click **Start Lab** → wait until icon turns **green**
* Click **AWS** to open the console

---

### **Step 2: Create EC2 Instance**

#### **Stage 1 — Name**

* Name: **ubuntu**

#### **Stage 2 — Select AMI**

* Select: **Ubuntu Server (Free-tier eligible)**

#### **Stage 3 — Architecture**

* Choose: **64-bit (x86)**

#### **Stage 4 — Instance Type**

* Select: **t2.micro**

#### **Stage 5 — Create Key Pair**

* Click **Create new key pair**
* Name it: e.g., **awskey**
* Download `.pem` file
* Save in a folder (e.g., **AWS/**)

#### **Stage 6 — Network Settings**

Enable:

* **SSH (22)**
* **HTTP (80)**
* **HTTPS (443)**
  Security group will be created.

#### **Stage 7 — Storage**

* Default: **8 GB**

#### **Stage 8 — Launch Instance**

* Click **Launch Instance**
* Wait until:

  * **Instance state = Running**
  * **Status checks = 2/2 passed**

---

## **Step 3: Connect Using SSH**

* Select instance → click **Connect**
* Go to **SSH client** tab
* Copy SSH command:

Example:

```
ssh -i "awskey.pem" ubuntu@ec2-xx-xx-xx-xx.compute-1.amazonaws.com
```

On your system:

```
cd <path-to-pem-file>
```

Example:

```
cd D:\AWS
```

Run the SSH command to access EC2.

---

## **Step 4: Install Required Software on EC2**

Run:

```
sudo apt update
sudo apt-get install docker.io -y
sudo apt install git -y
sudo apt install nano -y
```

---
/**
