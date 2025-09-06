# 🔐 Password Manager

A secure and user-friendly password management application that allows users to **store, generate, and manage passwords** for different accounts in one centralized location. Built with security-first principles to provide a safe and efficient way to handle multiple passwords without the need to remember them individually.

## 🚀 Features

### 🔑 Core Functionality
- **User Authentication** - Secure login/signup system to protect user data
- **Add / Store Passwords** - Save passwords with associated account details
- **Password Encryption** - All stored passwords are encrypted using industry-standard encryption
- **Password Generator** - Generate strong, random passwords with customizable parameters
- **Search & Retrieve** - Quickly find and access saved passwords
- **Update & Delete** - Complete CRUD operations for managing stored passwords

### 🛡️ Security Features
- **End-to-End Encryption** - Passwords encrypted before storage
- **Secure Authentication** - JWT-based authentication system
- **Password Hashing** - User passwords hashed using bcrypt
- **Session Management** - Secure session handling with automatic timeout
- **Data Validation** - Input sanitization and validation on all endpoints

## 🛠️ Technologies Used

### Frontend
- **HTML5** - Semantic markup and structure
- **CSS3** - Modern styling with responsive design
- **JavaScript (ES6+)** - Interactive client-side functionality
- **Bootstrap** *(Optional)* - Responsive UI components

### Backend
- **Node.js** - Server-side JavaScript runtime
- **Express.js** - Web application framework for API development
- **JWT (jsonwebtoken)** - Authentication and authorization
- **bcrypt.js** - Password hashing and encryption
- **crypto** - Additional encryption utilities

### Database
- **PostgreSQL** / **MongoDB** / **Firebase** - Secure data storage for user credentials and password data
- **Database Encryption** - Additional layer of data protection

### Development Tools
- **dotenv** - Environment variable management
- **nodemon** - Development server with auto-restart
- **cors** - Cross-origin resource sharing
- **helmet** - Security middleware for Express

## 📁 Project Structure

```
password-manager/
├── client/                 # Frontend files
│   ├── index.html         # Main HTML file
│   ├── style.css          # Main stylesheet
│   ├── script.js          # Client-side JavaScript
│   └── assets/            # Images and static files
├── server/                # Backend files
│   ├── controllers/       # Route controllers
│   ├── middleware/        # Custom middleware
│   ├── models/            # Database models
│   ├── routes/            # API routes
│   ├── utils/             # Utility functions
│   └── config/            # Configuration files
├── .env.example           # Environment variables template
├── .gitignore            # Git ignore file
├── package.json          # Dependencies and scripts
└── README.md             # Project documentation
```

## 🚦 Getting Started

### Prerequisites
- **Node.js** (v14 or higher)
- **npm** or **yarn** package manager
- **Database** (PostgreSQL/MongoDB/Firebase account)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Rewa17Shankar/project-password-manager.git
   cd project-password-manager
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   Create a `.env` file in the root directory:
   ```env
   # Database Configuration
   DATABASE_URL=your_database_connection_string
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=password_manager
   DB_USER=your_db_user
   DB_PASSWORD=your_db_password
   
   # JWT Configuration
   JWT_SECRET=your_super_secret_jwt_key
   JWT_EXPIRES_IN=24h
   
   # Encryption
   ENCRYPTION_KEY=your_32_character_encryption_key
   
   # Server Configuration
   PORT=3000
   NODE_ENV=development
   
   # CORS Configuration
   ALLOWED_ORIGINS=http://localhost:3000
   ```

4. **Database Setup**
   ```bash
   # For PostgreSQL
   npm run db:setup
   
   # Or manually create tables using provided SQL scripts
   ```

5. **Run the application**
   ```bash
   # Development mode
   npm run dev
   
   # Production mode
   npm start
   ```

6. **Access the application**
   Open your browser and navigate to `http://localhost:3000`

## 🎮 How to Use

### Getting Started
1. **Sign Up** - Create a new account with email and master password
2. **Log In** - Access your password vault with your credentials
3. **Add Passwords** - Store new passwords with account details
4. **Generate Passwords** - Use the built-in generator for strong passwords
5. **Search & Manage** - Find, edit, or delete stored passwords as needed

### Password Generator Options
- **Length**: 8-128 characters
- **Character Types**: Uppercase, lowercase, numbers, symbols
- **Exclude Similar**: Option to exclude similar-looking characters
- **Custom Rules**: Add specific requirements

## 🔒 Security Measures

### Data Protection
- **AES-256 Encryption** - Industry-standard encryption for stored passwords
- **Salted Password Hashing** - bcrypt with salt rounds for user passwords
- **Secure Headers** - Helmet.js for security headers
- **Input Validation** - Comprehensive input sanitization

### Authentication
- **JWT Tokens** - Stateless authentication with secure tokens
- **Session Timeout** - Automatic logout after inactivity
- **Rate Limiting** - Protection against brute force attacks
- **HTTPS Enforcement** - Secure data transmission

## 🚀 Deployment

### Environment Setup
The application can be deployed on various platforms:

- **Render** - Full-stack deployment with PostgreSQL
- **Vercel** - Frontend deployment with Serverless functions
- **Netlify** - Static frontend with Netlify Functions
- **Heroku** - Complete application deployment

### Deployment Checklist
- [ ] Set environment variables on hosting platform
- [ ] Configure database connection
- [ ] Enable HTTPS
- [ ] Set up monitoring and logging
- [ ] Configure backup strategy

## 🔧 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/verify` - Token verification

### Password Management
- `GET /api/passwords` - Get all user passwords
- `POST /api/passwords` - Add new password
- `GET /api/passwords/:id` - Get specific password
- `PUT /api/passwords/:id` - Update password
- `DELETE /api/passwords/:id` - Delete password

### Utilities
- `POST /api/generate` - Generate random password
- `GET /api/health` - Health check endpoint

## 🔮 Future Enhancements

### Planned Features
- **Multi-Device Sync** - Synchronization across devices
- **Browser Extensions** - Chrome/Firefox extensions
- **Two-Factor Authentication** - Additional security layer
- **Secure Notes** - Store sensitive text information
- **Password Sharing** - Securely share passwords with team members
- **Audit Logs** - Track password access and changes
- **Dark Mode** - Theme customization options
- **Mobile App** - iOS/Android native applications

### Scalability Improvements
- **Microservices Architecture** - Service separation for better scalability
- **Redis Caching** - Improved performance with caching
- **Load Balancing** - Handle increased user traffic
- **Backup & Recovery** - Automated backup systems

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Development Guidelines
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Standards
- Follow ESLint configuration
- Write unit tests for new features
- Update documentation as needed
- Follow security best practices

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Security Notice

This is an educational project. For production use, ensure:
- Regular security audits
- Compliance with data protection regulations
- Professional security review
- Regular dependency updates

## 📞 Contact

**Rewa Shankar**
- GitHub: [@Rewa17Shankar](https://github.com/Rewa17Shankar)
- Project Link: [https://github.com/Rewa17Shankar/project-password-manager](https://github.com/Rewa17Shankar/project-password-manager)

## 🙏 Acknowledgments

- Security best practices from OWASP
- Encryption standards from NIST
- Community feedback and contributions
- Open-source libraries and frameworks

---

⚠️ **Important**: Always keep your master password secure and consider using additional security measures like 2FA for enhanced protection.

⭐ If you found this project helpful, please consider giving it a star!
