# 📌 Static Websites with Docker & Nginx

This repository contains three static websites that can be served using **Docker and Nginx**. Each website is packaged inside its own Docker container for easy deployment and testing.

---

## 🚀 **Getting Started**
Follow these steps to **set up, build, and run** the websites on your local machine.

### **📌 Prerequisites**
Make sure you have the following installed:
- [Docker](https://www.docker.com/get-started) (Ensure Docker is running)

---

## 📥 **Clone the Repository**
First, clone the repository to your local machine:
```sh
git clone https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

---

## 🛠 **Building and Running the Websites**
Each website is in its own folder with a **Dockerfile**. Follow these steps for each website.

### **1️⃣ Running Site 1**
```sh
cd site1
docker build -t site1 .
docker run -d -p 8081:80 site1
```
🔹 Now, open **http://localhost:8081** in your browser.

### **2️⃣ Running Site 2**
```sh
cd ../site2
docker build -t site2 .
docker run -d -p 8082:80 site2
```
🔹 Now, open **http://localhost:8082** in your browser.

### **3️⃣ Running Site 3**
```sh
cd ../site3
docker build -t site3 .
docker run -d -p 8083:80 site3
```
🔹 Now, open **http://localhost:8083** in your browser.

---

## 🛑 **Stopping the Containers**
To stop all running containers:
```sh
docker ps  # Find the container IDs
docker stop <CONTAINER_ID>
```

To remove a container:
```sh
docker rm <CONTAINER_ID>
```

---

## 🧹 **Cleaning Up**
If you want to remove all Docker images for these websites:
```sh
docker rmi site1 site2 site3
```

To remove **unused** images and free up space:
```sh
docker image prune -f
```

---

## 🛠 **Troubleshooting**
### **1️⃣ Can't access the website?**
- Ensure Docker is running:  
  ```sh
  docker ps
  ```
- Restart the container:
  ```sh
  docker restart <CONTAINER_ID>
  ```
- Make sure no other applications are using ports **8081, 8082, or 8083**.

### **2️⃣ Need to rebuild after making changes?**
If you edit `index.html`, rebuild the image:
```sh
docker build -t site1 .
docker run -d -p 8081:80 site1
```

---

## 📌 **Keeping Containers Running After Closing the Terminal**
By default, if you close the terminal, the website **stops running**. To keep it running in the background, **run containers in detached mode (`-d`)**:
```sh
docker run -d -p 8081:80 site1
docker run -d -p 8082:80 site2
docker run -d -p 8083:80 site3
```

To make sure they restart automatically **even after a system reboot**:
```sh
docker run -d --restart unless-stopped -p 8081:80 site1
docker run -d --restart unless-stopped -p 8082:80 site2
docker run -d --restart unless-stopped -p 8083:80 site3
```

---

## 📜 **License**
This project is open-source under the **MIT License**.

---

🚀 **Happy Coding!**
