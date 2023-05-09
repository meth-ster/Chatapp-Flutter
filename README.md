# 🌟 Full Stack Realtime Chat App 🌟

Welcome to the **Full Stack Realtime Chat App** project! 🚀 This open-source project is built to provide a **real-time chat experience** using the latest technologies. Whether you're a seasoned developer or a beginner, we invite you to contribute and be a part of this exciting journey! 💻👾


![Login](./frontend/Public/login.png)



## Table of Contents
- [🔧 Tech Stack](#-tech-stack)
- [🛠️ Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Setup .env File](#setup-env-file)
  - [Building the Application](#building-the-application)
    - [Backend](#backend)
    - [Frontend](#frontend)
- [🤝 Contributing](#-contributing)
- [🎯 Future Plans](#-future-plans)
- [📜 License](#license)

---

## 🔧 Tech Stack
This application is built using the **MERN** stack with **Socket.io** for real-time messaging and **TailwindCSS** for UI design. Here’s the stack breakdown:

- **MongoDB**: NoSQL database for storing messages and user data.
- **Express**: Backend web framework for building RESTful APIs.
- **React**: Frontend framework for a dynamic user interface.
- **Node.js**: JavaScript runtime for server-side development.
- **Socket.io**: Enables real-time, bidirectional communication between the server and clients.
- **TailwindCSS**: Utility-first CSS framework for building modern, responsive UIs.
- **DaisyUI**: A component library built on top of TailwindCSS for faster UI development.
- **JWT Authentication**: Secure user authentication using JSON Web Tokens.
- **Zustand**: A state management library for React.



---

## 🛠️ Getting Started

Follow these simple steps to get the project up and running on your local machine.

### Prerequisites
Before you start, ensure you have the following installed:

- **Node.js** (v14 or higher)
- **Docker** (for containerizing the app)
- **Git** (to clone the repository)

### Setup .env File
1. Navigate to the `backend` directory.
2. Create a `.env` file and add the following content (you may need to modify the values according to your setup):

```env
MONGODB_URI=mongodb://localhost:27017/chatapp
JWT_SECRET=your_jwt_secret_key
PORT=5001
```
### This file is crucial for defining the environment variables that the backend will use.

---

## 🛠️ Getting Started

Follow these simple steps to get the project up and running on your local Host using docker.

```bash
git clone https://github.com/yourusername/full-stack-realtime-chat-app.git
```

```bash
cd full-stack-chatApp
```
## Create a Docker network:

```bash
docker network create full-stack
```

## Building the frontend.

```bash
cd frontend
```

```bash
docker build -t fullstack_frontend .
```

### Run the Frontend container:

```bash
docker run -d --network=full-stack  -p 5173:5173 --name frontend frontend:latest
```
#### The frontend will now be accessible on port 5173.


## Run the MongoDB Container:

```bash
docker run -d -p 27017:27017 --name mongo mongo:latest
```
---

## Building the Backend

```bash
cd backend
```

### Build the Backend image:

```bash
docker build -t fullstack_backend .
```

### Run the Backend container:

```bash
docker run -d --network=full-stack --add-host=host.docker.internal:host-gateway -p 5001:5001 --env-file .env backend
```
#### This will build and run the backend container, exposing the backendAPI on port 5001.

`Backend API: http://localhost:5001`

### To Verify the conncetion between backend and databse:
```bash
docker logs < backend-container-id >
```

### Once the backend and frontend containers are running, you can access the application in your browser:

`Frontend: http://localhost:5173`


You can now interact with the real-time chat app and start messaging!

---

## 🤝 Contributing
We welcome contributions from developers of all skill levels! Here's how you can contribute:

**Report bugs:** If you encounter any bugs or issues, please open an issue with detailed information.
**Suggest features:** Have an idea for a new feature? Open an issue to discuss it with the community.
**Submit pull requests:** If you have a fix or a feature you'd like to contribute, submit a pull request. Ensure your changes pass any linting or tests, if applicable.
To get started, fork the repository and create your branch for the feature or bug fix you're working on.

---

## 🎯 Future Plans
This project is evolving, and here are a few exciting things on the horizon:

CI/CD Pipelines: We plan to implement Continuous Integration and Continuous Deployment pipelines to automate testing and deployment.
Kubernetes (K8s): Kubernetes manifests will be added for container orchestration to deploy the app on cloud platforms like AWS, GCP, or Azure.
Stay tuned for updates as we continue to improve and expand this project!

---
## 📚 Project Snapshots:

![Settings](./frontend/Public/settings.png)

![chat](./frontend/Public/chat.png)

![logout](./frontend/Public/logout.png)


---

## 📜 License
This project is licensed under the MIT License. See the LICENSE file for more details.