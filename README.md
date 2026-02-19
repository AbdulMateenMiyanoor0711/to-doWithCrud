# Todo List App ✅

A full-stack task management web application built with React, Vite, Express, and MySQL to help you organize, track, and complete your daily tasks effortlessly.

![React](https://img.shields.io/badge/React-19.2.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-7.2.4-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Express](https://img.shields.io/badge/Express-5.2.1-000000?style=for-the-badge&logo=express&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

## 📸 Preview

<!-- Add your screenshots here -->
https://github.com/user-attachments/assets/b26200cb-f8a6-4763-8317-a4a95676c021

## ✨ Features

- **➕ Add Tasks**: Quickly add new tasks with a task name
- **✅ Toggle Status**: Mark tasks as active or inactive with a checkbox toggle
- **🗑️ Delete Tasks**: Remove individual tasks with a single click
- **🧹 Bulk Delete**: Delete all tasks at once with the "Delete All" button
- **📊 Active Task Counter**: Real-time count of remaining active tasks
- **📱 Responsive Design**: Works seamlessly on all devices
- **🎨 Modern UI**: Clean and intuitive interface with CSS Modules styling
- **⚡ Real-Time Updates**: Task list refreshes automatically after every operation

## 🛠️ Technologies Used

### Frontend

- **React 19.2.0**: Modern UI library with hooks
- **Vite 7.2.4**: Lightning-fast build tool and dev server
- **CSS Modules**: Scoped, modular styling for components
- **ESLint**: Code quality and linting

### Backend

- **Express 5.2.1**: Fast and minimalist web framework for Node.js
- **MySQL2**: MySQL database driver with Promise support
- **CORS**: Cross-Origin Resource Sharing middleware
- **dotenv**: Environment variable management

## 📋 Project Structure

```
TODO/
├── client/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Delete.jsx             # Delete button component with SVG icon
│   │   │   └── Deletelist.jsx         # Delete all tasks button component
│   │   ├── assets/                    # Static assets
│   │   ├── App.jsx                    # Main app with CRUD operations
│   │   ├── App.module.css             # Component styles (CSS Modules)
│   │   ├── App.css                    # Additional component styles
│   │   ├── index.css                  # Global styles
│   │   └── main.jsx                   # Application entry point
│   ├── public/                        # Static assets
│   ├── index.html                     # HTML template
│   ├── package.json                   # Frontend dependencies
│   └── vite.config.js                 # Vite configuration
├── server/
│   ├── controller/
│   │   └── todo.controller.js         # Todo CRUD operations (DB queries)
│   ├── routes/
│   │   └── todo.route.js              # Todo API route definitions
│   ├── models/                        # Database models (reserved)
│   ├── db.js                          # MySQL database connection pool
│   ├── index.js                       # Express server entry point
│   ├── .env                           # Environment variables
│   └── package.json                   # Backend dependencies
├── backend/                           # Legacy backend directory
└── README.md                          # Project documentation
```

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- **Node.js** (v18 or higher)
- **npm** or **pnpm** package manager
- **MySQL** (v8 or higher)

### Database Setup

1. **Create the database and table**

   ```sql
   CREATE DATABASE test2;

   USE test2;

   CREATE TABLE todolist (
     id INT AUTO_INCREMENT PRIMARY KEY,
     taskname VARCHAR(255) NOT NULL,
     status ENUM('active', 'inactive') DEFAULT 'active'
   );
   ```

2. **Update database credentials**

   Edit `server/db.js` with your MySQL credentials:

   ```javascript
   const connection = mysql.createPool({
     host: "localhost",
     user: "root",
     password: "YOUR_PASSWORD",
     database: "test2",
     port: 3306,
   });
   ```

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/AbdulMateenMiyanoor0711/to-doWithCrud.git
   ```

2. **Navigate to project directory**

   ```bash
   cd to-doWithCrud
   ```

3. **Install frontend dependencies**

   ```bash
   cd client
   npm install
   cd ..
   ```

4. **Install backend dependencies**

   ```bash
   cd server
   npm install
   cd ..
   ```

5. **Start the backend server**

   ```bash
   cd server
   node index.js
   ```

6. **Start the frontend dev server** (in a new terminal)

   ```bash
   cd client
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
node index.js    # Start the Express server on port 8000
```

## 🔌 API Endpoints

### Tasks

| Method | Endpoint             | Description          |
| ------ | -------------------- | -------------------- |
| GET    | `/todo-list`         | Get all tasks        |
| POST   | `/todo-add`          | Add a new task       |
| PUT    | `/todo-edit`         | Toggle task status   |
| PATCH  | `/update-status/:id` | Update task status   |
| DELETE | `/delete-todo/:id`   | Delete a single task |
| DELETE | `/todo-truncate`     | Delete all tasks     |

## 💡 How to Use

1. **Add Tasks**: Type a task name in the input field and click "Add" or press Enter
2. **Toggle Status**: Click the checkbox next to a task to mark it as active/inactive
3. **Delete Tasks**: Click the 🗑️ trash icon on any task to remove it
4. **Bulk Delete**: Click "🗑️ Delete All" at the bottom to clear all tasks
5. **Track Progress**: View the active task count at the bottom of the list

## 🎨 Features in Detail

### Task Management

- Create tasks with descriptive names
- Toggle task completion status with intuitive checkbox interface
- Completed tasks are visually distinguished with strikethrough styling
- Delete individual tasks instantly
- Bulk delete all tasks with one click
- Real-time task list updates after every operation

### UI/UX Design

- **CSS Modules**: Scoped styling prevents class name collisions
- **SVG Icons**: Custom delete button with inline SVG icon
- **Status Badges**: Color-coded active/inactive status indicators
- **Empty State**: Friendly message when no tasks exist ("No tasks yet — add something ✨")
- **Disabled Button**: Add button is disabled when input is empty
- **Accessible**: Proper `aria-label` attributes on interactive elements

### Architecture

- **MVC Pattern**: Clean separation of concerns with controllers, routes, and views
- **Connection Pooling**: MySQL2 connection pool for efficient database connections
- **Promise-Based**: Async/await throughout the backend for clean asynchronous code
- **Component-Based**: Reusable React components for UI elements

## 🔄 Future Enhancements

- [ ] Task categories and tags
- [ ] Search and filter tasks
- [ ] Task descriptions and details
- [ ] Due dates and reminders
- [ ] Dark mode support
- [ ] Drag and drop task reordering
- [ ] User authentication and personal task lists
- [ ] Export task list to CSV/PDF
- [ ] Task priority levels (High, Medium, Low)
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
- The `backend/` directory contains a legacy empty `index.js` file
- No confirmation dialog before bulk delete operation

## 📧 Contact

**Abdul Mateen Miyanoor**

- GitHub: [@AbdulMateenMiyanoor0711](https://github.com/AbdulMateenMiyanoor0711)
- Project Link: [https://github.com/AbdulMateenMiyanoor0711/to-doWithCrud](https://github.com/AbdulMateenMiyanoor0711/to-doWithCrud)

---

<div align="center">

⭐ If you found this helpful, please give it a star! ⭐

![GitHub stars](https://img.shields.io/github/stars/AbdulMateenMiyanoor0711/to-doWithCrud?style=social)
![GitHub forks](https://img.shields.io/github/forks/AbdulMateenMiyanoor0711/to-doWithCrud?style=social)

Made with ❤️ by Abdul Mateen Miyanoor

</div>
