# 🔐 Password Manager

A full-stack password management application built with **React.js**, **Node.js**, and **MongoDB**. This secure application allows users to store, generate, and manage passwords for different accounts in one centralized, encrypted location.

## 🚀 Features

### 🔑 Core Functionality
- **User Authentication** - Secure JWT-based login/signup system
- **Password Storage** - Encrypted password storage with account details
- **Password Generator** - Generate strong, customizable passwords
- **Search & Filter** - Quick search and categorization of stored passwords
- **CRUD Operations** - Add, view, update, and delete password entries
- **Responsive Design** - Mobile-friendly interface with modern UI

### 🛡️ Security Features
- **AES-256 Encryption** - Client-side encryption before database storage
- **Password Hashing** - Bcrypt hashing for user authentication
- **JWT Authentication** - Stateless authentication with secure tokens
- **Input Validation** - Comprehensive validation on both client and server
- **Secure Headers** - Protection against common web vulnerabilities
- **Session Management** - Automatic logout and token refresh

## 🛠️ Tech Stack

### Frontend (React.js)
- **React.js** - Component-based UI library
- **Vite** - Fast build tool and development server
- **Tailwind CSS** - Utility-first CSS framework for styling
- **React Router** - Client-side routing
- **Axios** - HTTP client for API requests
- **React Hook Form** - Form handling and validation
- **Crypto-JS** - Client-side encryption utilities

### Backend (Node.js)
- **Node.js** - JavaScript runtime environment
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database for data storage
- **Mongoose** - MongoDB object modeling
- **JWT** - JSON Web Tokens for authentication
- **bcrypt** - Password hashing library
- **helmet** - Security middleware
- **cors** - Cross-origin resource sharing
- **dotenv** - Environment variable management

### Development Tools
- **ESLint** - Code linting and formatting
- **Prettier** - Code formatting
- **Nodemon** - Development server auto-restart
- **Concurrently** - Run multiple scripts simultaneously

## 📁 Project Structure

```
project-password-manager/
├── backend/                    # Node.js Express server
│   ├── node_modules/          # Backend dependencies
│   ├── .env                   # Environment variables
│   ├── package-lock.json      # Lock file
│   ├── package.json           # Backend dependencies
│   └── server.js              # Main server file
│
├── public/                    # Static assets
│
├── src/                       # React frontend source
│   ├── assets/               # Images, icons, static files
│   ├── components/           # Reusable React components
│   ├── App.css              # Main application styles
│   ├── App.jsx              # Root React component
│   ├── index.css            # Global CSS styles
│   └── main.jsx             # React entry point
│
├── .eslintrc.js              # ESLint configuration
├── .gitignore               # Git ignore rules
├── index.html               # HTML template
├── package-lock.json        # Frontend lock file
├── package.json             # Frontend dependencies
├── passop.zip              # Project archive
├── postcss.config.js       # PostCSS configuration
├── README.md               # Project documentation
├── tailwind.config.js      # Tailwind CSS configuration
└── vite.config.js          # Vite configuration
```

## 🚦 Getting Started

### Prerequisites
- **Node.js** (v16 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas)
- **Git**

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Rewa17Shankar/project-password-manager.git
   cd project-password-manager
   ```

2. **Backend Setup**
   ```bash
   cd backend
   npm install
   ```

3. **Frontend Setup**
   ```bash
   # Go back to root directory
   cd ..
   npm install
   ```

4. **Environment Configuration**
   Create a `.env` file in the `backend` directory:
   ```env
   # MongoDB Configuration
   MONGODB_URI=mongodb://localhost:27017/password-manager
   # OR for MongoDB Atlas:
   # MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/password-manager
   
   # JWT Configuration
   JWT_SECRET=your_super_secret_jwt_key_here
   JWT_EXPIRES_IN=7d
   
   # Server Configuration
   PORT=5000
   NODE_ENV=development
   
   # Encryption
   ENCRYPTION_SECRET=your_32_character_encryption_secret
   
   # CORS Configuration
   CLIENT_URL=http://localhost:5173
   ```

5. **Database Setup**
   ```bash
   # Start MongoDB service (if running locally)
   mongod
   
   # The application will automatically create the database and collections
   ```

6. **Start the Application**
   
   **Option 1: Run both servers separately**
   ```bash
   # Terminal 1 - Backend server
   cd backend
   npm run dev
   
   # Terminal 2 - Frontend development server
   # From root directory
   npm run dev
   ```
   
   **Option 2: Run both servers concurrently**
   ```bash
   # From root directory (if concurrently is set up)
   npm run dev:full
   ```

7. **Access the Application**
   - **Frontend**: http://localhost:5173
   - **Backend API**: http://localhost:5000

## 🎮 Usage Guide

### Getting Started
1. **Register** - Create a new account with email and master password
2. **Login** - Access your secure password vault
3. **Add Password** - Store new passwords with website/app details
4. **Generate Password** - Use the built-in secure password generator
5. **Manage Passwords** - Search, edit, or delete stored credentials

### Password Generator Features
- **Customizable Length** (8-128 characters)
- **Character Options**: Uppercase, lowercase, numbers, symbols
- **Exclude Ambiguous** characters option
- **Copy to Clipboard** functionality
- **Strength Indicator** visual feedback

## 🔒 Security Implementation

### Frontend Security
- **Client-Side Encryption** - Passwords encrypted before sending to server
- **Input Sanitization** - XSS prevention through input validation
- **Secure Storage** - JWT tokens stored in httpOnly cookies (if implemented)
- **Auto-Logout** - Session timeout for inactive users

### Backend Security
- **Password Hashing** - bcrypt with salt rounds
- **JWT Authentication** - Stateless token-based auth
- **Rate Limiting** - Brute force attack prevention
- **CORS Protection** - Controlled cross-origin requests
- **Helmet Middleware** - Security headers implementation

### Database Security
- **Data Encryption** - Sensitive data encrypted at rest
- **Connection Security** - Secure MongoDB connection strings
- **Access Control** - User-based data isolation
- **Backup Strategy** - Regular encrypted backups

## 🛠️ API Endpoints

### Authentication Routes
```
POST /api/auth/register    - User registration
POST /api/auth/login       - User login
POST /api/auth/logout      - User logout
GET  /api/auth/verify      - Token verification
POST /api/auth/refresh     - Refresh JWT token
```

### Password Management Routes
```
GET    /api/passwords      - Get user's passwords
POST   /api/passwords      - Create new password entry
GET    /api/passwords/:id  - Get specific password
PUT    /api/passwords/:id  - Update password entry
DELETE /api/passwords/:id  - Delete password entry
```

### Utility Routes
```
POST /api/generate         - Generate secure password
GET  /api/health          - Health check
GET  /api/stats           - User statistics
```

## 🎨 Frontend Components

### Component Structure
```
src/components/
├── Auth/
│   ├── Login.jsx         # Login form component
│   ├── Register.jsx      # Registration form
│   └── ProtectedRoute.jsx # Route protection
├── Dashboard/
│   ├── Dashboard.jsx     # Main dashboard
│   ├── PasswordList.jsx  # Password entries list
│   └── SearchBar.jsx     # Search functionality
├── Password/
│   ├── AddPassword.jsx   # Add new password
│   ├── EditPassword.jsx  # Edit existing password
│   ├── PasswordCard.jsx  # Individual password display
│   └── PasswordGenerator.jsx # Password generator
├── UI/
│   ├── Header.jsx        # Navigation header
│   ├── Footer.jsx        # Application footer
│   ├── Loading.jsx       # Loading spinner
│   └── Modal.jsx         # Reusable modal component
└── Common/
    ├── ErrorBoundary.jsx # Error handling
    └── Toast.jsx         # Notification system
```

## 📱 Responsive Design

- **Mobile-First Approach** - Optimized for mobile devices
- **Tailwind CSS** - Responsive utilities and components
- **Progressive Web App** features (if implemented)
- **Touch-Friendly** interface elements
- **Cross-Browser** compatibility

## 🚀 Deployment

### Frontend Deployment (Vercel/Netlify)
```bash
# Build the frontend
npm run build

# Deploy to Vercel
vercel --prod

# Or deploy to Netlify
netlify deploy --prod
```

### Backend Deployment (Render/Railway)
```bash
# Set environment variables on hosting platform
# Deploy backend server
# Configure MongoDB Atlas connection
```

### Environment Variables for Production
```env
NODE_ENV=production
MONGODB_URI=your_production_mongodb_uri
JWT_SECRET=your_production_jwt_secret
CLIENT_URL=https://your-frontend-domain.com
```

## 🔧 Development Scripts

### Frontend Scripts
```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint
```

### Backend Scripts
```bash
cd backend
npm run start        # Start production server
npm run dev          # Start development server with nodemon
npm run test         # Run tests (if implemented)
```

## 🧪 Testing

### Frontend Testing
```bash
# Unit tests for components
npm run test

# E2E tests
npm run test:e2e
```

### Backend Testing
```bash
cd backend
npm run test         # API endpoint tests
npm run test:coverage # Test coverage report
```

## 🔮 Future Enhancements

### Planned Features
- **Two-Factor Authentication** (2FA) - Additional security layer
- **Password Sharing** - Secure password sharing between users
- **Browser Extension** - Chrome/Firefox extension integration
- **Mobile App** - React Native mobile application
- **Biometric Authentication** - Fingerprint/Face ID support
- **Password Audit** - Security analysis and breach checking
- **Secure Notes** - Store sensitive text information
- **Team Management** - Organization and team password sharing

### Technical Improvements
- **PWA Implementation** - Offline functionality
- **Real-time Sync** - WebSocket-based synchronization
- **Advanced Encryption** - Zero-knowledge architecture
- **Performance Optimization** - Code splitting and lazy loading
- **Automated Testing** - Comprehensive test suite
- **CI/CD Pipeline** - Automated deployment workflow

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Run tests and linting**
   ```bash
   npm run lint
   npm run test
   ```
5. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
6. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
7. **Open a Pull Request**

### Development Guidelines
- Follow the existing code style and conventions
- Write meaningful commit messages
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting PR

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Security Disclaimer

This application is designed with security best practices, but for production use, please ensure:

- Regular security audits
- Compliance with data protection regulations (GDPR, CCPA, etc.)
- Professional security review
- Regular dependency updates
- Secure hosting environment
- Regular backups and disaster recovery planning

## 📞 Contact & Support

**Developer**: Rewa Shankar
- **GitHub**: [@Rewa17Shankar](https://github.com/Rewa17Shankar)
- **Project Repository**: [project-password-manager](https://github.com/Rewa17Shankar/project-password-manager)

### Getting Help
- **Issues**: Report bugs or request features via GitHub Issues
- **Discussions**: Join project discussions for questions and ideas
- **Documentation**: Check the wiki for additional documentation

## 🙏 Acknowledgments

- **Security Standards**: OWASP guidelines and security best practices
- **Open Source Libraries**: All the amazing open-source contributors
- **Community Feedback**: Users and contributors who helped improve the project
- **Educational Resources**: Various tutorials and documentation that guided development

---

<img width="1292" height="587" alt="image" src="https://github.com/user-attachments/assets/58335d97-3130-47e3-81d1-7242018ca50d" />
<img width="1293" height="597" alt="image" src="https://github.com/user-attachments/assets/3885d1e2-79ed-4b3e-89b6-011868a2d48b" />
<img width="1012" height="183" alt="image" src="https://github.com/user-attachments/assets/2a17057a-b0a0-4b5e-9951-5e277050ec15" />

