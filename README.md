# Project List Manager 📋

A full-stack project management web application built with React, Vite, Express, and MySQL to help you organize and track your projects effortlessly with secure user authentication.

![React](https://img.shields.io/badge/React-19.2.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-7.2.4-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Express](https://img.shields.io/badge/Express-5.2.1-000000?style=for-the-badge&logo=express&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

## 📸 Preview

<!-- Add your screenshots here -->
<!-- <img width="1920" height="1200" alt="Dashboard Screenshot" src="YOUR_SCREENSHOT_URL" /> -->
<!-- <img width="1920" height="1200" alt="Login Screenshot" src="YOUR_SCREENSHOT_URL" /> -->

## ✨ Features

- **🔐 User Authentication**: Secure registration and login system with password hashing
- **➕ Add Projects**: Quickly add new projects with a project name
- **✏️ Edit Projects**: Modify existing project names via modal popup
- **🗑️ Delete Projects**: Remove individual projects with a single click
- **🧹 Bulk Delete**: Delete all projects at once with confirmation modal
- **🔑 Password Hashing**: Argon2id password hashing for secure authentication
- **🍪 Cookie-Based Auth**: Persistent login sessions using cookies
- **🛡️ Protected Routes**: Dashboard accessible only to authenticated users
- **📱 Responsive Design**: Works seamlessly on all devices
- **🎨 Modern UI**: Clean and intuitive interface with custom CSS styling

## 🛠️ Technologies Used

### Frontend

- **React 19.2.0**: Modern UI library with hooks
- **Vite 7.2.4**: Lightning-fast build tool and dev server
- **React Router DOM 7.13.0**: Client-side routing and navigation
- **js-cookie**: Cookie management for authentication
- **Custom CSS**: Hand-crafted styles for a polished look

### Backend

- **Express 5.2.1**: Fast and minimalist web framework for Node.js
- **MySQL2**: MySQL database driver with Promise support
- **Argon2**: Industry-standard password hashing algorithm
- **CORS**: Cross-Origin Resource Sharing middleware
- **Nodemon**: Auto-restart dev server on file changes

## 📋 Project Structure

```
PROJECT-LIST/
├── src/
│   ├── components/
│   │   ├── Dashboard.jsx          # Project dashboard with CRUD operations
│   │   ├── Login.jsx              # User login form
│   │   └── Project.jsx            # User registration form
│   ├── support/
│   │   └── auth.js                # Cookie-based authentication utility
│   ├── assets/                    # Static assets
│   ├── App.jsx                    # Main app with routing
│   ├── App.css                    # Component styles
│   ├── index.css                  # Global styles
│   └── main.jsx                   # Application entry point
├── backend/
│   ├── controllers/
│   │   ├── auth.controller.js     # User registration & login logic
│   │   └── project.controller.js  # Project CRUD operations
│   ├── routes/
│   │   ├── auth.route.js          # Authentication API routes
│   │   └── project.route.js       # Project API routes
│   ├── utils/
│   │   └── hashed.js              # Argon2 password hashing utility
│   ├── _test/
│   │   └── hashed.test.js         # Unit tests for password hashing
│   ├── db.js                      # MySQL database connection pool
│   ├── index.js                   # Express server entry point
│   └── package.json               # Backend dependencies
├── public/                        # Static assets
├── index.html                     # HTML template
├── package.json                   # Frontend dependencies & scripts
└── vite.config.js                 # Vite configuration
```

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- **Node.js** (v18 or higher)
- **npm** or **yarn** package manager
- **MySQL** (v8 or higher)

### Database Setup

1. **Create the database and tables**

   ```sql
   CREATE DATABASE projectdetails;

   USE projectdetails;

   CREATE TABLE users (
     id INT AUTO_INCREMENT PRIMARY KEY,
     Name VARCHAR(255) NOT NULL,
     Email VARCHAR(255) NOT NULL UNIQUE,
     Password VARCHAR(255) NOT NULL
   );

   CREATE TABLE project (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(255) NOT NULL
   );
   ```

2. **Update database credentials**

   Edit `backend/db.js` with your MySQL credentials:

   ```javascript
   const connection = mysql.createPool({
     host: "localhost",
     user: "root",
     password: "YOUR_PASSWORD",
     database: "projectdetails",
     port: 3306,
   });
   ```

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/AbdulMateenMiyanoor0711/project-list.git
   ```

2. **Navigate to project directory**

   ```bash
   cd project-list
   ```

3. **Install frontend dependencies**

   ```bash
   npm install
   ```

4. **Install backend dependencies**

   ```bash
   cd backend
   npm install
   cd ..
   ```

5. **Start the backend server**

   ```bash
   cd backend
   node index.js
   ```

6. **Start the frontend dev server** (in a new terminal)

   ```bash
   npm run dev
   ```

7. **Open your browser**
   ```
   Visit http://localhost:5173
   ```

## 📦 Available Scripts

### Frontend

```bash
npm run dev      # Start development server with HMR
npm run build    # Build for production
npm run preview  # Preview production build locally
npm run lint     # Run ESLint to check code quality
```

### Backend

```bash
node index.js    # Start the Express server on port 9000
```

## 🔌 API Endpoints

### Authentication

| Method | Endpoint       | Description         |
| ------ | -------------- | ------------------- |
| POST   | `/add-user`    | Register a new user |
| POST   | `/verify-user` | Login & verify user |

### Projects

| Method | Endpoint            | Description             |
| ------ | ------------------- | ----------------------- |
| GET    | `/project/all`      | Get all projects        |
| POST   | `/project/add`      | Add a new project       |
| PATCH  | `/project/edit`     | Edit a project name     |
| DELETE | `/project/delete`   | Delete a single project |
| DELETE | `/project/truncate` | Delete all projects     |

## 💡 How to Use

1. **Register**: Create an account with your name, email, and password
2. **Login**: Sign in with your registered email and password
3. **Add Projects**: Enter a project name and click "Add" to create a new project
4. **Edit Projects**: Click "Edit" on any project to modify its name via a modal popup
5. **Delete Projects**: Click "Delete" to remove a single project
6. **Bulk Delete**: Click "Delete All Projects" and confirm to clear all projects
7. **Logout**: Your session persists for 7 days via secure cookies

## 🎨 Features in Detail

### User Authentication

- Secure registration with Argon2id password hashing
- Login with email and password verification
- Cookie-based session management (7-day expiry)
- Protected dashboard route - redirects unauthenticated users to login

### Project Management

- Create projects with unique names
- Edit project names through an intuitive modal interface
- Delete individual projects instantly
- Bulk delete all projects with a confirmation dialog
- Real-time project list updates after every operation

### Security

- **Argon2id Hashing**: Industry-standard password hashing with configurable memory, time, and parallelism costs
- **Secure Cookies**: HTTP-only, secure, SameSite strict cookie settings
- **CORS Enabled**: Cross-Origin Resource Sharing for safe API communication

## 🔄 Future Enhancements

- [ ] JWT-based token authentication
- [ ] Project categories and tags
- [ ] Search and filter projects
- [ ] Project descriptions and details
- [ ] Team collaboration & sharing
- [ ] Dark mode support
- [ ] Drag and drop project reordering
- [ ] Export project list to CSV/PDF
- [ ] Project deadlines and reminders
- [ ] Activity log and audit trail

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🐛 Known Issues

- Database credentials are hardcoded in `db.js` (use environment variables in production)
- No input sanitization for SQL queries (consider using parameterized queries)
- Token validation logic is placeholder (needs backend session table integration)
- Edit modal uses inline styles instead of CSS classes

## 📧 Contact

**Abdul Mateen Miyanoor**

- GitHub: [@AbdulMateenMiyanoor0711](https://github.com/AbdulMateenMiyanoor0711)
- Project Link: [https://github.com/AbdulMateenMiyanoor0711/project-list](https://github.com/AbdulMateenMiyanoor0711/project-list)

---

<div align="center">

⭐ If you found this helpful, please give it a star! ⭐

![GitHub stars](https://img.shields.io/github/stars/AbdulMateenMiyanoor0711/project-list?style=social)
![GitHub forks](https://img.shields.io/github/forks/AbdulMateenMiyanoor0711/project-list?style=social)

Made with ❤️ by Abdul Mateen Miyanoor

</div>
