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

<img width="1105" height="592" alt="image" src="https://github.com/user-attachments/assets/94950902-2bf9-4677-b397-06a2c5066c36" />


- Next use the command `npm.init` to initialise your project, so that a new file named `package.json` will be created.
- Follow the prompts after running the command. Press `Enter` several times to accept default values, the accept to write out the `package.json` file by typing yes.
- Run the command `ls` to confirm that you have `package.json` file created.

<img width="881" height="549" alt="image" src="https://github.com/user-attachments/assets/6fb444ff-69a7-4e46-8ac8-d6309dbdf038" />

---

### **Install ExpressJS**
- To install express, install it using npm:

```
npm install express
```

- Next, create the file `index.js` with the command below:

```
touch index.js
```

- Run `ls` to confirm that your `index.js file is successfully created.
- Install the `dotenv` module

```
npm install dotenv
```

- Open the `index.js` file.

```
vim index.js
```

- Type the code below into it and save.

```
const express = require('express');
require('dotenv').config();

const app = express();

const port = process.env.PORT || 5000;

app.use((req, res, next) => {
  res.header("Access-Control-Allow-Origin", "\*");
  res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
  next();
});

app.use((req, res, next) => {
  res.send('Welcome to Express');
});

app.listen(port, () => {
  console.log(`Server running on port ${port}`)
});
```

- Notice that we have specified to use port `5000` in the code. This will be required later when we go on the browser.
- Use `:w` to save in `vim` and use `:qa` to exit `vim`

- Let’s start the server to see if it works.
- Open your terminal in the same directory as your `index.js` file and type:

```
node index.js
```

- You shoud see `Server running on port 5000` in your terminal.

-Open this port in `EC2 Security Groups`. Check Project 1 Step 1 - Installing the `Nginx Web Server`. There we created an inbound rule to open `TCP port 80`, you need to do the same for `port 5000`, like this:

- Open your browser and access your server's `Public IP` or `Public DNS` name followed by `port 5000`:

```
http://<PublicIP-or-PublicDNS>:5000
```

### 📍**Routes**
- There are three actions that our To-Do application needs to be able to do: `Create a new task` `Display list of all tasks` `Delete a completed task`
- Each task will be associated with some particular endpoint and will use different standard HTTP request methods: `POST` `GET` `DELETE`.
- For each task, we need to create `routes` that will define various endpoints that the `To-do` app will depend on.

-Let us create a folder `routes`

```
mkdir routes
```

- Change directory to `routes` folder.

```
cd routes
```

- Create a file `api.js` with the command below.

```
touch api.js
```

- Open the file with the command below.

```
vim api.js
```

-Type the below code in the file.

```
const express = require ('express');
const router = express.Router();

router.get('/todos', (req, res, next) => {

});

router.post('/todos', (req, res, next) => {

});

router.delete('/todos/:id', (req, res, next) => {

});

module.exports = router;
```

