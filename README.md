Payment Portal
This project is a secure payment portal that allows customers to register, log in, and make payments. It also includes an admin dashboard for managing payments, with static admin credentials for demonstration purposes. The portal is built using a Node.js backend with Express and MongoDB for the database, and a React frontend for the user interface.

Table of Contents
Overview
Features
Technologies Used
Getting Started
API Endpoints
Security Measures
Group Members
References
Overview
This project was developed as a group assignment. It consists of a backend server created with Node.js, Express, and MongoDB, and a frontend application built with React. The application supports:

User registration and login with secure authentication.
Payment processing for customers.
Admin functionality for viewing and managing payments.
Features
User Registration and Login: Allows customers to create an account and log in to the portal.
Static Admin Login: Admin credentials are hardcoded for demonstration purposes, allowing quick access to the admin dashboard.
JWT Authentication: Secures API endpoints by requiring a JSON Web Token (JWT) for authorization.
SSL Encryption: The server is configured to run over HTTPS for secure data transmission, using SSL certificates.
Admin Dashboard: Admins can view all payments, process payments, and delete payments if needed.
Rate Limiting and Helmet Security: Protects the application from basic security threats and rate limiting to prevent abuse.
Technologies Used
Backend: Node.js, Express, MongoDB
Frontend: React, Axios
Security: SSL/TLS for HTTPS, Helmet for securing HTTP headers, bcrypt for password hashing, JWT for authentication, and rate limiting to prevent DDoS attacks.
Getting Started
Prerequisites
Node.js: Make sure you have Node.js installed on your machine.
MongoDB: Set up MongoDB, either locally or using a cloud provider like MongoDB Atlas.
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/your-repo-url.git
cd payment-portal
Install dependencies for backend and frontend:

bash
Copy code
# For backend
cd backend
npm install

# For frontend
cd ../frontend
npm install
Set up the environment variables.

Create a .env file in the backend folder with the following information:

plaintext
Copy code
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
PORT=443
Add SSL certificates:

Place the SSL certificate and private key files in the backend/certs directory. Name them server.cert and server.key, respectively.

Start the backend server:

bash
Copy code
cd backend
node server.js
Start the frontend:

bash
Copy code
cd ../frontend
npm start
API Endpoints
Auth Routes
POST /api/auth/register - Register a new user
POST /api/auth/login - Log in an existing user or admin
Payment Routes
POST /api/payment - Process a payment (Customer-only)
GET /api/admin/payments - View all payments (Admin-only)
DELETE /api/admin/payments/:id - Delete a specific payment (Admin-only)
PUT /api/admin/payments/:id/process - Mark a payment as processed (Admin-only)
Security Measures
The application includes the following security features:

JWT Authentication: All routes are secured with JWT tokens to ensure that only authenticated users can access them.
Password Hashing: User passwords are hashed using bcrypt for added security.
Rate Limiting: Express-rate-limit is used to limit the number of requests a user can make in a specific time frame, preventing DDoS attacks.
Helmet: Helmet is used to set various HTTP headers to secure the app.
SSL Encryption: SSL/TLS certificates are used to ensure that data transmitted between the client and server is encrypted.
Static Admin Login: Hardcoded credentials allow easy access to the admin portal for testing.
Input Validation: Basic input validation is implemented to prevent injection attacks.
Group Members
Rishkaar Sunnylall
Aaron [Last Name]
Zayn [Last Name]
References
Express Documentation: https://expressjs.com/
MongoDB Documentation: https://docs.mongodb.com/
React Documentation: https://reactjs.org/
JWT Documentation: https://jwt.io/
Bcrypt Documentation: https://www.npmjs.com/package/bcrypt
Helmet Documentation: https://helmetjs.github.io/
Express Rate Limit Documentation: https://www.npmjs.com/package/express-rate-limit
