# HRM Management System

A comprehensive Human Resource Management System built with the MERN stack (MongoDB, Express.js, React, Node.js).

## Features

- **Role-based Authentication**: 7 different user roles with hierarchical access control
- **Secure Login System**: JWT-based authentication with password hashing
- **Responsive Dashboard**: Role-specific dashboards with relevant features
- **User Management**: Admin capabilities for user creation and management
- **Protected Routes**: Frontend route protection based on user roles

## User Roles

1. **Admin** - Full system access
2. **Vice President (VP)** - High-level management access
3. **HR BP (Business Partner)** - Strategic HR access
4. **HR Manager** - HR department management
5. **HR Executive** - HR operations
6. **Team Manager** - Team management
7. **Team Leader (TL)** - Team leadership

## Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication tokens
- **bcryptjs** - Password hashing
- **CORS** - Cross-origin resource sharing
- **express-validator** - Input validation

### Frontend
- **React** - UI library
- **React Router** - Client-side routing
- **Axios** - HTTP client
- **Bootstrap 5** - CSS framework
- **Bootstrap Icons** - Icon library

## Project Structure

```
hrm-management/
├── backend/
│   ├── config/
│   │   └── database.js
│   ├── controllers/
│   │   ├── authController.js
│   │   └── userController.js
│   ├── middleware/
│   │   └── auth.js
│   ├── models/
│   │   └── User.js
│   ├── routes/
│   │   ├── auth.js
│   │   └── users.js
│   ├── .env
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── Dashboard.js
│   │   │   ├── Login.js
│   │   │   └── ProtectedRoute.js
│   │   ├── context/
│   │   │   └── AuthContext.js
│   │   ├── utils/
│   │   │   └── api.js
│   │   ├── App.js
│   │   └── index.js
│   ├── .env
│   └── package.json
└── README.md
```

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or yarn

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd hrm-management/backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Configure environment variables in `.env`:
   ```env
   PORT=5000
   NODE_ENV=development
   MONGODB_URI=mongodb://localhost:27017/hrm_management
   JWT_SECRET=your_super_secret_jwt_key_here_change_in_production
   JWT_EXPIRE=7d
   CLIENT_URL=http://localhost:3000
   ```

4. Start the backend server:
   ```bash
   npm run dev
   ```

The backend server will run on `http://localhost:5000`

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd hrm-management/frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Configure environment variables in `.env`:
   ```env
   REACT_APP_API_URL=http://localhost:5000/api
   REACT_APP_NAME=HRM Management System
   REACT_APP_VERSION=1.0.0
   ```

4. Start the frontend development server:
   ```bash
   npm start
   ```

The frontend application will run on `http://localhost:3000`

## API Endpoints

### Authentication Routes
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get current user profile
- `GET /api/auth/verify` - Verify JWT token
- `POST /api/auth/logout` - User logout

### User Routes
- `GET /api/users` - Get all users (Admin/VP only)
- `GET /api/users/:id` - Get user by ID
- `POST /api/users` - Create new user (Admin only)
- `PUT /api/users/:id` - Update user
- `GET /api/users/roles` - Get all available roles

### Health Check
- `GET /api/health` - Server health check

## Usage

### Creating the First Admin User

Since there's no signup functionality, you'll need to create the first admin user directly in the database. You can use MongoDB Compass, MongoDB shell, or any MongoDB client:

```javascript
// Example admin user document
{
  "email": "admin@company.com",
  "password": "$2a$12$hashedPasswordHere", // Use bcrypt to hash the password
  "firstName": "System",
  "lastName": "Administrator",
  "role": "Admin",
  "department": "IT",
  "employeeId": "ADMIN001",
  "isActive": true
}
```

### Login Process

1. Navigate to `http://localhost:3000`
2. You'll be redirected to the login page
3. Enter your credentials
4. Upon successful login, you'll be redirected to the dashboard

### Role-based Access

- **Admin**: Can access all features including user management
- **VP**: Can view executive dashboard and user lists
- **HR Roles**: Can access HR-specific features
- **Team Roles**: Can access team management features

## Security Features

- **Password Hashing**: All passwords are hashed using bcrypt
- **JWT Authentication**: Secure token-based authentication
- **Role-based Access Control**: Hierarchical permission system
- **Input Validation**: Server-side validation for all inputs
- **CORS Protection**: Configured for specific origins
- **Protected Routes**: Frontend route protection

## Development

### Backend Development
```bash
cd backend
npm run dev  # Uses nodemon for auto-restart
```

### Frontend Development
```bash
cd frontend
npm start  # React development server with hot reload
```

## Production Deployment

### Environment Variables
Make sure to update the following for production:
- `JWT_SECRET`: Use a strong, unique secret
- `MONGODB_URI`: Point to your production database
- `NODE_ENV`: Set to "production"
- `CLIENT_URL`: Set to your production frontend URL

### Build Frontend
```bash
cd frontend
npm run build
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the ISC License.

## Support

For support and questions, please contact the development team or create an issue in the repository.
#   H R M - n e w  
 #   H R M - n e w  
 #   H R M - n e w  
 #   H R M - n e w  
 