# Hotel Booking (HOTEL-v2-FINAL-)

**HOTEL-v2-FINAL-** is a hotel booking application that allows users to search for hotels, book rooms, manage their bookings and accounts. The application provides REST API for interacting with hotel, room, and booking data.

---

## 📋 Key Features

### 🏨 Hotel and Room Management
- View hotel list with filtering by city and category
- Get detailed information about specific hotels
- View available rooms in hotels

### 📅 Room Booking
- Create, edit, and delete bookings
- Filter bookings by user and date
- Bulk booking of multiple rooms

### 👥 Users and Accounts
- User registration and authentication
- User profile management

### 📊 Analytics and Logging
- Booking statistics tracking
- Logging of all operations
- Get logs for specified period

### 🔗 REST API
- Documentation using Swagger
- Support for integration with external services

---

## 📸 Application Mockups

### 🔐 Login Window
![Login](https://images/Screenshot%25202025-10-08%2520at%252021.20.28.png)

### 🔐 Registration Window
![Registration](https://images/Screenshot%25202025-10-08%2520at%252021.20.33.png)

### Main Page
![Main Page](https://images/Screenshot%25202025-10-08%2520at%252021.24.17.png)

### ⚙️ Admin Panel for Room Management
![Admin Room Management](https://images/Screenshot%25202025-10-08%2520at%252021.27.28.png)

### ⚙️ Admin Panel for User Management
![Admin User Management](https://images/Screenshot%25202025-10-08%2520at%252021.15.27.png)

---

## 🛠 Tech Stack

### Backend (Spring Boot)
- **Programming Language:** Java 17
- **Framework:** Spring Boot 3.x
- **Database:** PostgreSQL
- **Build System:** Maven
- **API Documentation:** Swagger
- **Containerization:** Docker

### Frontend (React)
- **Framework:** Create React App
- **Language:** JavaScript
- **Build Tool:** npm
- **Development Server:** React Scripts

---

## 📁 Project Structure

HOTEL-v2-FINAL-/
├── backend/ # Spring Boot backend
│ ├── src/ # Java source code
│ ├── pom.xml # Maven configuration
│ └── HELP.md # Backend documentation
├── frontend/ # React frontend
│ ├── src/ # React source code
│ ├── public/ # Static files
│ └── package.json # npm dependencies
├── docs/ # Project documentation
├── images/ # Application screenshots
└── README.md # This file


---

## ⚙️ Installation and Launch

### Requirements
- Java 17 or newer
- Maven
- Node.js (for frontend)
- PostgreSQL
- Docker (optional, for containerization)

### Backend Setup
```bash
# Navigate to backend directory
cd backend

# Build project
mvn clean install

# Run application
mvn spring-boot:run

## ⚙️ Frontend Setup
```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Start development server
npm start



# Clone repository
git clone https://github.com/magodididi/HOTEL-v2-FINAL-.git
cd HOTEL-v2-FINAL-

# Start backend (in one terminal)
cd backend && mvn spring-boot:run

# Start frontend (in another terminal)
cd frontend && npm start
# Build and run with Docker Compose
docker-compose up -d

### 🔗 API Documentation
After launching the backend application, Swagger documentation is available at:
http://localhost:8080/swagger-ui.html

### 🚀 Quick Start
Start PostgreSQL database
Run backend application on port 8080
Run frontend application on port 3000
Access the application at http://localhost:3000
Register a new account or login
Start exploring hotels and making bookings

### 📚 Available Scripts
Backend Scripts
mvn clean install       # Build the project
mvn spring-boot:run     # Run the application
mvn test                # Run tests
Frontend Scripts
npm start               # Runs the app in development mode
npm test                # Launches the test runner
npm run build           # Builds the app for production
npm run eject           # Ejects from Create React App (one-way operation)
### 🔧 Configuration
Backend Configuration
Edit backend/src/main/resources/application.properties:
spring.datasource.url=jdbc:postgresql://localhost:5432/hotel_booking
spring.datasource.username=your_username
spring.datasource.password=your_password
server.port=8080
Frontend Configuration
The frontend is configured to proxy API requests to the backend on port 8080.
### 🐳 Docker Deployment
# Build and run all services
docker-compose up -d

# Stop services
docker-compose down

### 🧪 Testing
Backend Tests
cd backend
mvn test
Frontend Tests
cd frontend
npm test

### 🤝 Contributing
Fork the repository
Create a feature branch:
git checkout -b feature/amazing-feature
Commit your changes:
git commit -m 'Add some amazing feature'
Push to the branch:
git push origin feature/amazing-feature
Open a Pull Request

### 📝 License
This project is for educational purposes.
