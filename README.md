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
## **Step 5: Create & Upload index.html (Local System)**

1. Create a folder **Example**
2. Add `index.html`
3. Open Git Bash inside folder:

```
git init
git add .
git commit -m "first commit"
```
4. Create GitHub repo → copy HTTPS URL
5. Push the code:

```
git branch -M main
git remote add origin <github-url>
git push -u origin main
```

---
**/
## **Step 6: Clone Repo on EC2**

```url:https://github.com/sonthepranavi/website-project.git
git clone <github-repo-url>
cd <folder>
ls
```

---

## **Step 7: Create Dockerfile**

```
nano Dockerfile
```

Paste:

```
FROM nginx
COPY . /usr/share/nginx/html
```

Save:
**Ctrl + O → Enter → Ctrl + X**

---

## **Step 8: Build Docker Image**

```
sudo docker build -t mywebapp .
```

---

## **Step 9: Run Docker Container**

```
sudo docker run -d -p 80:80 mywebapp
```

---

## **Step 10: Test Deployment**

* Go to EC2 → select instance
* Copy **Public IPv4 address**
* Paste in browser:

```
http://<public-ip>
```
//
Your **index.html** should open.

---

## **Step 11: Stop & Cleanup**

Stop container:

```
sudo docker ps
sudo docker stop <container-id>
```

Terminate instance:

* EC2 → Instances
* Select instance
* **Instance state → Terminate**

Finally → **End Lab**

# awscomm
