# Real-Time Chat Application

## Project Summary

The Real-Time Chat Application is a comprehensive full-stack web solution that enables users to communicate with each other in real-time. Built with modern technologies including React, Node.js, Express, MongoDB, and Socket.io, the application provides a seamless messaging experience with instant message delivery, online status tracking, and image sharing capabilities.

### Overview
This is a full-featured chat platform where users can create accounts, authenticate securely with JWT tokens, and instantly exchange messages with other registered users. The application features a responsive design built with Tailwind CSS, real-time bidirectional communication using Socket.io WebSockets, and a robust backend API for user and message management. The frontend leverages React with Redux Toolkit for efficient state management, while the backend implements a clean architecture with dedicated controllers, routes, and middleware for authentication and file handling.

### Core Features
- **User Authentication System**: Secure sign up, login, and logout with JWT token-based authentication
- **Real-Time Messaging**: Instant message delivery and receipt using Socket.io WebSocket connections
- **Online Status**: Real-time visibility of which users are currently online
- **Image Sharing**: Upload and share images in conversations with Cloudinary integration
- **User Profiles**: Create, view, and manage user profiles with profile pictures
- **Responsive UI**: Beautiful, mobile-friendly interface with Tailwind CSS styling
- **State Management**: Redux Toolkit for centralized and predictable state management
- **Security**: Password encryption with bcryptjs and secure token handling

### Architecture
The application follows a client-server architecture with clear separation of concerns. The **Backend** (Node.js/Express) handles authentication, user management, message persistence in MongoDB, and real-time communication through Socket.io. The **Frontend** (React/Vite) provides an interactive user interface with Redux for state management and Socket.io client for real-time communication. Custom React hooks manage API calls for users, messages, and authentication state.

### Technology Stack
**Backend**: Express.js, Node.js, MongoDB, Mongoose, Socket.io, JWT, Bcryptjs, Cloudinary, Multer, CORS, Cookie-parser
**Frontend**: React, Vite, Redux Toolkit, React Router, Socket.io-client, Axios, Tailwind CSS, React Icons, ESLint

---

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Socket Events](#socket-events)
- [File Structure Details](#file-structure-details)
- [Environment Variables](#environment-variables)

---

## ✨ Features

- **User Authentication**: Sign up, login, and logout functionality with JWT tokens
- **Real-Time Messaging**: Send and receive messages instantly using Socket.io
- **Online Status**: See which users are currently online
- **User Profiles**: View and manage user profiles
- **Image Sharing**: Share images in conversations with Cloudinary integration
- **Responsive Design**: Beautiful UI built with Tailwind CSS
- **State Management**: Redux toolkit for efficient state management
- **Secure Passwords**: Passwords are encrypted using bcryptjs

---

## 🛠 Tech Stack

### Backend
- **Express.js** - Web framework
- **Node.js** - JavaScript runtime
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **Socket.io** - Real-time bidirectional communication
- **JWT** - Authentication tokens (jsonwebtoken)
- **Bcryptjs** - Password hashing
- **Cloudinary** - Image management
- **Multer** - File upload handling
- **CORS** - Cross-origin requests
- **Cookie-parser** - Cookie parsing middleware

### Frontend
- **React** - UI library
- **Vite** - Build tool
- **Redux Toolkit** - State management
- **React Router DOM** - Routing
- **Socket.io-client** - WebSocket client
- **Axios** - HTTP client
- **Tailwind CSS** - Styling
- **React Icons** - Icon library
- **Emoji Picker React** - Emoji selection
- **ESLint** - Code linting
- **PostCSS** - CSS processing

---

## 📁 Project Structure

```
Real_Time_Chat_Application/
├── backend/
│   ├── config/
│   │   ├── cloudinary.js       # Cloudinary configuration
│   │   ├── db.js               # MongoDB connection
│   │   └── token.js            # JWT token generation
│   ├── controllers/
│   │   ├── auth.controllers.js  # Authentication logic
│   │   ├── message.controllers.js # Message handling
│   │   └── user.controllers.js  # User management
│   ├── middlewares/
│   │   ├── isAuth.js           # Authentication middleware
│   │   └── multer.js           # File upload middleware
│   ├── models/
│   │   ├── user.model.js       # User schema
│   │   ├── message.model.js    # Message schema
│   │   └── conversation.model.js # Conversation schema
│   ├── routes/
│   │   ├── auth.routes.js      # Auth endpoints
│   │   ├── user.routes.js      # User endpoints
│   │   └── message.routes.js   # Message endpoints
│   ├── socket/
│   │   └── socket.js           # Socket.io configuration
│   ├── public/                 # Static files
│   ├── .env                    # Environment variables
│   ├── .gitignore             # Git ignore rules
│   ├── index.js               # Server entry point
│   └── package.json           # Dependencies
│
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── MessageArea.jsx      # Main messaging component
    │   │   ├── ReceiverMessage.jsx  # Received message display
    │   │   ├── SenderMessage.jsx    # Sent message display
    │   │   └── SideBar.jsx          # Navigation sidebar
    │   ├── customHooks/
    │   │   ├── getCurrentUser.jsx   # Fetch current user
    │   │   ├── getMessages.jsx      # Fetch messages
    │   │   └── getOtherUsers.jsx    # Fetch other users
    │   ├── pages/
    │   │   ├── Home.jsx             # Main chat page
    │   │   ├── Login.jsx            # Login page
    │   │   ├── SignUp.jsx           # Registration page
    │   │   └── Profile.jsx          # User profile page
    │   ├── redux/
    │   │   ├── store.js             # Redux store configuration
    │   │   ├── userSlice.js         # User state slice
    │   │   └── messageSlice.js      # Message state slice
    │   ├── assets/                  # Static assets
    │   ├── App.jsx                  # Main App component
    │   ├── index.css                # Global styles
    │   ├── main.jsx                 # React entry point
    │   └── vite.config.js           # Vite configuration
    ├── public/                      # Public files
    ├── .gitignore                   # Git ignore rules
    ├── eslint.config.js             # ESLint configuration
    ├── index.html                   # HTML template
    ├── package.json                 # Dependencies
    ├── postcss.config.js            # PostCSS configuration
    ├── tailwind.config.js           # Tailwind CSS configuration
    └── vite.config.js               # Vite build configuration
```

---

## 🚀 Installation

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn
- MongoDB (local or Atlas)
- Cloudinary account (optional, for image uploads)

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the backend directory with the following variables:
```
PORT=5000
MONGODB_URL=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. The frontend is configured to connect to `http://localhost:5000` by default. Update the configuration in [frontend/src/main.jsx](frontend/src/main.jsx) if needed.

---

## ⚙️ Configuration

### Backend Configuration Files

#### [config/db.js](backend/config/db.js)
- Connects to MongoDB using Mongoose
- Uses `MONGODB_URL` from environment variables

#### [config/token.js](backend/config/token.js)
- Generates JWT tokens for authenticated users
- Token expires in 7 days

#### [config/cloudinary.js](backend/config/cloudinary.js)
- Configures Cloudinary for image uploads
- Handles image storage and retrieval

#### [socket/socket.js](backend/socket/socket.js)
- Creates HTTP server and Socket.io instance
- Manages user connections and online status
- CORS configured for frontend URL

---

## 🏃 Running the Application

### Start Backend Server

```bash
cd backend
npm run dev
```

Server will start on `http://localhost:5000`

### Start Frontend Development Server

In a new terminal:
```bash
cd frontend
npm run dev
```

Frontend will be available at `http://localhost:5173`

---

## 🔌 API Endpoints

### Authentication Routes (`/api/auth`)

| Method | Endpoint | Description | Body |
|--------|----------|-------------|------|
| POST | `/signup` | Register new user | `{ userName, email, password }` |
| POST | `/login` | Login user | `{ email, password }` |
| GET | `/logout` | Logout user | - |

### User Routes (`/api/user`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/getall` | Get all users |
| GET | `/getme` | Get current user |
| PUT | `/edit` | Update user profile |

### Message Routes (`/api/message`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/send/:id` | Send message to user |
| GET | `/get/:id` | Get messages with user |
| POST | `/image/:id` | Send image message |

---

## 🔄 Socket Events

### Client to Server

| Event | Data | Description |
|-------|------|-------------|
| `connection` | `{ userId }` | User connects (via query param) |
| `disconnect` | - | User disconnects |

### Server to Client

| Event | Data | Description |
|-------|------|-------------|
| `getOnlineUsers` | `[userId, ...]` | List of online user IDs |

---

## 📋 File Structure Details

### Backend

#### [models/user.model.js](backend/models/user.model.js)
User schema with fields:
- `name` - User's display name
- `userName` - Unique username (required)
- `email` - Unique email (required)
- `password` - Hashed password (required)
- `image` - Profile image URL
- `timestamps` - Created and updated dates

#### [models/message.model.js](backend/models/message.model.js)
Message schema with fields:
- `sender` - Reference to User who sent the message
- `receiver` - Reference to User who receives the message
- `message` - Text content
- `image` - Image URL
- `timestamps` - Created and updated dates

#### [controllers/auth.controllers.js](backend/controllers/auth.controllers.js)
- `signUp` - Create new user account
- `login` - Authenticate user
- `logOut` - Clear user session

#### [middlewares/isAuth.js](backend/middlewares/isAuth.js)
- Verifies JWT token from cookies
- Sets `req.userId` for authenticated requests

### Frontend

#### [redux/userSlice.js](frontend/src/redux/userSlice.js)
Manages user state:
- `userData` - Current user information
- `socket` - Socket.io connection instance
- `onlineUsers` - List of online users

#### [redux/messageSlice.js](frontend/src/redux/messageSlice.js)
Manages message state:
- `messages` - Array of messages
- `selectedUser` - Currently selected chat user

#### [customHooks/getCurrentUser.jsx](frontend/src/customHooks/getCurrentUser.jsx)
Fetches and sets current user data on app load

#### [customHooks/getOtherUsers.jsx](frontend/src/customHooks/getOtherUsers.jsx)
Fetches list of all available users for messaging

#### [customHooks/getMessages.jsx](frontend/src/customHooks/getMessages.jsx)
Fetches conversation history with selected user

#### [components/MessageArea.jsx](frontend/src/components/MessageArea.jsx)
Main messaging interface component

#### [components/SenderMessage.jsx](frontend/src/components/SenderMessage.jsx)
Displays sent messages with styling

#### [components/ReceiverMessage.jsx](frontend/src/components/ReceiverMessage.jsx)
Displays received messages with styling

#### [components/SideBar.jsx](frontend/src/components/SideBar.jsx)
Navigation sidebar with user list

#### [pages/Home.jsx](frontend/src/pages/Home.jsx)
Main chat page integrating all components

#### [pages/Login.jsx](frontend/src/pages/Login.jsx)
User login interface

#### [pages/SignUp.jsx](frontend/src/pages/SignUp.jsx)
User registration interface

#### [pages/Profile.jsx](frontend/src/pages/Profile.jsx)
User profile management page

---

## 🔐 Environment Variables

### Backend (.env)

```env
# Server Configuration
PORT=5000

# Database Configuration
MONGODB_URL=mongodb+srv://user:password@cluster.mongodb.net/database-name

# JWT Configuration
JWT_SECRET=your_secret_key_here

# Cloudinary Configuration (Optional)
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

### Frontend Configuration

Server URL is defined in [frontend/src/main.jsx](frontend/src/main.jsx):
```javascript
export const serverUrl = "http://localhost:5000";
```

---

## 🔑 Key Features Explained

### Real-Time Messaging
- Uses Socket.io to establish WebSocket connections
- Messages are instantly delivered to both sender and receiver
- Online/offline status updates in real-time

### Authentication
- User sign-up with email validation and unique username
- Passwords are hashed using bcryptjs with salt rounds of 10
- JWT tokens stored in HTTP-only cookies for security
- 7-day token expiration for session management

### State Management
- Redux Toolkit for centralized state management
- Separate slices for user and message state
- Efficient state updates and subscriptions

---

## 🛡️ Security Features

- **Password Hashing**: bcryptjs with 10 salt rounds
- **JWT Tokens**: Secure token-based authentication
- **HTTP-Only Cookies**: Prevent XSS attacks
- **CORS**: Restricted to frontend origin
- **Environment Variables**: Sensitive data in .env files
- **Authentication Middleware**: Protected routes with isAuth middleware

---

## 📝 Scripts

### Backend
- `npm run dev` - Start development server with nodemon

### Frontend
- `npm run dev` - Start Vite development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

---

## 🐛 Troubleshooting

### Connection Issues
- Ensure MongoDB is running and `MONGODB_URL` is correct
- Check if port 5000 is not in use
- Verify CORS configuration matches your frontend URL

### Socket.io Issues
- Check if origin in socket configuration matches frontend URL
- Ensure Socket.io client version matches server version
- Check browser console for WebSocket connection errors

### Authentication Issues
- Verify `JWT_SECRET` is set in environment variables
- Check if cookies are enabled in the browser
- Ensure token expiration time is configured correctly

---

## 📄 License

ISC License

---

## 👨‍💻 Author

Created by Chandan Kumar

---

## 🚀 Future Enhancements

- [ ] Group chat functionality
- [ ] Voice and video calling
- [ ] Message encryption
- [ ] Read receipts
- [ ] Typing indicators
- [ ] Message reactions
- [ ] File sharing improvements
- [ ] User blocking feature
- [ ] Search functionality
- [ ] Message search and history

---

## 📞 Support

For issues or questions, please contact the development team or create an issue in the repository.



- **Email**: chandankumarnwd9060@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/chandan-kumar-12bb24284/
- **GitHub**: https://github.com/CHANDANKUMAR45
