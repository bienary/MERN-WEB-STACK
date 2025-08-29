# 🍃 MERN-WEB-STACK

## 🎯**DevOps/Cloud Engineering > MERN WEB STACK**
📌 **MERN Web Stack** is a powerful JavaScript-based framework for building full-stack web applications. It seamlessly connects the database, backend, and frontend, allowing developers to create dynamic, scalable, and high-performance applications using a single programming language from start to finish.

**🧰MERN Web Stack consists of following components:**

> M — `MongoDB` → A document-based, No-SQL database used to store application data in a form of documents.

> E — `Express.js` → A sever side Web Application framework for Node.js.

> R — `React.js` → A frontend framework developed by facebook. It is based on `JavaScript`, used to build User Interface (UI) components.

> N — `Node.js` → A JavaScript runtime environment. It is used to run JavaScript on a machine rather than in a browser.

<img width="1024" height="451" alt="image" src="https://github.com/user-attachments/assets/1f747e01-deb0-461f-a4c6-66b7f01eca54" />

---
## **STEP 0 ~ PREPARING PREREQUISITES**
- To complete this project you will need an AWS account and a virtual server with Ubuntu Server OS.
- Sign in to AWS free tier account and create a new EC2 Instance of t3.micro family with Ubuntu Server 24.04.
- After creating your EC2 Instances, you can add  `Tag Name` to it with a value that corresponds to a current project you are working on.

<img width="1352" height="509" alt="image" src="https://github.com/user-attachments/assets/a0effa94-5709-4643-8261-8ae231c6820a" />

---
- You can also set up your `Mobaxterm` to connect to EC2 Instances.

![mobaxterm ssh login](https://github.com/user-attachments/assets/96beff79-b751-4fea-b757-a1ef7ce1ff1a)

---
**STEP 1 ~ BACKEND CONFIGURATION**

Update Ubuntu
```
sudo apt update
```

Upgrade Ubuntu
```
sudo apt upgrade
```

Lets get the location of `Node.js` software from Ubuntu repositories.

```
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```

<img width="1004" height="423" alt="image" src="https://github.com/user-attachments/assets/09cfc8f1-1cd2-4059-9739-ab7cfcb3a3ac" />

### **Install Node.js on the server**

`NPM` is a package manager for Node like apt for Ubuntu, it is used to install Node modules & packages and to manage dependency conflicts.
- Run the command below to install both `nodejs` and `npm.`

```
sudo apt-get install -y nodejs
```

- Verify the node installation with the command below.

```
node -v
```

- Verify the node installation with the command below.

```
npm -v
```

### **Application Code Setup**

- Create a new directory for your `To-DO` project:

```
mkdir Todo
```

Run the command below to verify that the `Todo` directory is created with `ls` command.

```
ls
```

📝 To see more useful information about files and directories, use the following combination of keys `ls -lih`. You can learn more about different useful keys for `ls` command with `ls --help`.

- Change your curruent directory to the newly created one:

```
cd Todo
```

