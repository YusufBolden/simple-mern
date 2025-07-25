# 🔧 Simple MERN

A full-stack MERN (MongoDB, Express, React, Node.js) application for managing tasks. This project was forked from [jmsv/simple-mern](https://github.com/jmsv/simple-mern) and configured for deployment using Render.

![React](https://img.shields.io/badge/-React-61DAFB?logo=react&logoColor=white&style=for-the-badge)
![Node.js](https://img.shields.io/badge/-Node.js-339933?logo=node.js&logoColor=white&style=for-the-badge)
![Express](https://img.shields.io/badge/-Express-000000?logo=express&logoColor=white&style=for-the-badge)
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?logo=mongodb&logoColor=white&style=for-the-badge)
![Render](https://img.shields.io/badge/-Render-46E3B7?logo=render&logoColor=white&style=for-the-badge)


---

## 🚀 Live Demo

- **Frontend** (Static Site): [https://simple-mern-frontend.onrender.com](https://simple-mern-frontend.onrender.com)
- **Backend** (Web Service API): [https://simple-mern-backend.onrender.com/api/tasks](https://simple-mern-backend.onrender.com/api/tasks)

---

## ✨ Features

- 📝 Add tasks with a simple UI
- 🗃 Tasks persist using MongoDB Atlas
- 🚀 Frontend and backend fully deployed on Render
- 🔄 Real-time task display
- 🔐 API communication over HTTPS with CORS enabled

---
## 🖥️ Local Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YusufBolden/simple-mern.git
cd simple-mern
```

### 2. Install Backend Dependencies

```bash
npm install
```

### 3. Set Up Environment Variables

Create a `.env` file at the **project root**:

```env
PORT=5000
MONGODB_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/<dbname>?retryWrites=true&w=majority
```

### 4. Run the Application Locally

```bash
npm run dev
```

### 5. Run Frontend Locally (Optional)

```bash
cd client
npm install
npm start
```

---

## ☁️ Deployment Instructions (Render)

### 🔹 Backend – Web Service

1. Go to [https://dashboard.render.com](https://dashboard.render.com)
2. Click **“New → Web Service”**
3. Connect your GitHub and select this repo
4. **Settings**:

| Field             | Value            |
|------------------|------------------|
| Root Directory   | *leave blank*    |
| Build Command    | `npm install`    |
| Start Command    | `node index.js`  |
| Environment      | Node             |

5. **Environment Variables**:

```env
MONGODB_URI=your_mongo_uri
PORT=10000
```

6. Deploy — copy the backend URL (used in frontend)

### 🔹 Frontend – Static Site

1. Go to **Render → New → Static Site**
2. Select the same repo
3. **Settings**:

| Field             | Value                          |
|------------------|----------------------------------|
| Root Directory   | `client`                         |
| Build Command    | `npm install && npm run build`   |
| Publish Directory| `build`                          |

4. (Optional) **Environment Variable**

| Key           | Value                      |
|---------------|----------------------------|
| `NODE_OPTIONS`| `--openssl-legacy-provider`|

5. Deploy — copy the frontend URL

---

## 🔄 Connecting Frontend to Backend

In `client/src/App.js`, use:

```js
const API_BASE = "https://simple-mern-backend.onrender.com";
```

Then redeploy the static site.

---

## 🧪 API Endpoints

| Method | Endpoint                | Description         |
|--------|-------------------------|---------------------|
| GET    | `/api/tasks`            | Fetch all tasks     |
| POST   | `/api/tasks/add`        | Add a new task      |

---

## 🛡 CORS Setup

To enable CORS in the backend, add this to `index.js`:

```js
const cors = require('cors');
app.use(cors());
```

---

## 🧑🏿‍💻 Author

Created by **Yusuf Bolden**. Feedback and collaboration welcome!

---

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).