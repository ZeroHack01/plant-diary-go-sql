# 🌱 Plant Diary - Go SQL Edition

<div align="center">

```ascii
    🌿 🌱 🌿 🌱 🌿 🌱 🌿
   ╔════════════════════════╗
   ║    PLANT DIARY v2.0    ║
   ║   Digital Garden Log   ║
   ╚════════════════════════╝
    🌿 🌱 🌿 🌱 🌿 🌱 🌿
```

[![Go](https://img.shields.io/badge/Go-1.18+-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://golang.org/)
[![Echo](https://img.shields.io/badge/Echo-Framework-orange?style=for-the-badge&logo=go&logoColor=white)](https://echo.labstack.com/)
[![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white)](https://vuejs.org/)
[![SQLite](https://img.shields.io/badge/SQL-Database-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)

**🌿 Track • 📷 Capture • 📊 Analyze • 🌱 Grow**

*A modern, full-stack plant tracking application for gardening enthusiasts*

</div>

---

## 🌟 Project Overview

**Plant Diary Go SQL** is a complete rewrite of the original Plant Diary application, featuring a powerful **Go + Echo** backend and an elegant **Vue.js** frontend. This digital gardening companion helps you track your plants' growth, manage photos, and maintain detailed records of your green friends.

> 🚀 **Version 2.0** - Enhanced with modern tech stack and improved features

### ✨ **What Makes This Special**

- 🏗️ **Modern Architecture**: Clean separation between backend API and frontend
- 📸 **Photo Management**: Upload, store, and organize plant photos in database
- 🌱 **Plant Tracking**: Comprehensive plant record management
- ⚡ **High Performance**: Fast Go backend with Echo framework
- 🎨 **Beautiful UI**: Responsive Vue.js interface
- 💾 **Reliable Storage**: SQL database for data persistence

---

## 🛠️ Tech Stack

<table>
<tr>
<td width="50%">

### 🔧 **Backend**
- **Language**: Go 1.18+
- **Framework**: Echo (High-performance HTTP)
- **Database**: SQL (SQLite/PostgreSQL/MySQL)
- **Features**: RESTful API, File Upload, CRUD Operations

</td>
<td width="50%">

### 🎨 **Frontend**
- **Framework**: Vue.js 3
- **Styling**: Modern CSS/SCSS
- **Features**: Reactive UI, Photo Gallery, Form Management
- **Build**: Vite/Webpack

</td>
</tr>
</table>

---

## 🚀 Quick Start

### 📋 **Prerequisites**

```bash
# Required Software
✅ Go 1.18 or higher
✅ Node.js 16+ and npm/yarn
✅ Git
✅ SQL Database (SQLite recommended for development)
```

### ⚡ **Installation & Setup**

<details>
<summary>🔽 <strong>Step-by-Step Installation</strong></summary>

#### 1️⃣ **Clone the Repository**
```bash
git clone https://github.com/NK-GO/plant-diary-go-sql.git
cd plant-diary-go-sql
```

#### 2️⃣ **Backend Setup**
```bash
# Install Go dependencies
go mod tidy

# Set up environment variables
cp .env.example .env
# Edit .env with your database configuration

# Initialize database
go run main.go migrate

# Start the backend server
go run main.go
# Backend runs on http://localhost:8080
```

#### 3️⃣ **Frontend Setup**
```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install
# or
yarn install

# Start development server
npm run dev
# or
yarn dev
# Frontend runs on http://localhost:3000
```

#### 4️⃣ **Access the Application**
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:8080
- **API Documentation**: http://localhost:8080/docs (if available)

</details>

### 🐳 **Docker Setup** (Optional)

```bash
# Build and run with Docker Compose
docker-compose up -d

# Access the application
# Frontend: http://localhost:3000
# Backend: http://localhost:8080
```

---

## 🌟 Features

### 🌱 **Core Plant Management**

<table>
<tr>
<td width="33%" align="center">

### 📝 **Plant Records**
- Add new plants to your collection
- Track planting dates and locations
- Record plant species and varieties
- Add personal notes and observations

</td>
<td width="33%" align="center">

### 📷 **Photo Management**
- Upload multiple photos per plant
- Store images directly in database
- View photo history and progress
- Delete unwanted photos

</td>
<td width="33%" align="center">

### 📊 **Growth Tracking**
- Monitor plant development
- Record watering schedules
- Track fertilization dates
- Note seasonal changes

</td>
</tr>
</table>

### 🔧 **Technical Features**

```bash
✅ RESTful API with Echo framework
✅ Responsive Vue.js frontend
✅ SQL database integration
✅ File upload and management
✅ CRUD operations for plants
✅ Image storage in database
✅ Modern ES6+ JavaScript
✅ Cross-platform compatibility
```

---

## 📖 API Documentation

### 🌐 **Core Endpoints**

| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|--------------|
| `GET` | `/api/plants` | List all plants | - |
| `POST` | `/api/plants` | Create new plant | `Plant JSON` |
| `GET` | `/api/plants/:id` | Get plant details | - |
| `PUT` | `/api/plants/:id` | Update plant | `Plant JSON` |
| `DELETE` | `/api/plants/:id` | Delete plant | - |
| `POST` | `/api/plants/:id/photos` | Upload photo | `multipart/form-data` |
| `DELETE` | `/api/photos/:id` | Delete photo | - |

### 📷 **Photo Upload Example**

```javascript
// Upload plant photo
const formData = new FormData();
formData.append('photo', fileInput.files[0]);
formData.append('description', 'New leaf growth');

fetch('/api/plants/123/photos', {
  method: 'POST',
  body: formData
});
```

### 🌱 **Plant Model Example**

```json
{
  "id": 1,
  "name": "Monstera Deliciosa",
  "species": "Monstera deliciosa",
  "plantedDate": "2024-01-15",
  "location": "Living Room Window",
  "notes": "Fast-growing, loves indirect light",
  "photos": [
    {
      "id": 1,
      "filename": "monstera_001.jpg",
      "uploadDate": "2024-01-15T10:30:00Z",
      "description": "Initial planting"
    }
  ]
}
```

---

## 🗂️ Project Structure

```
plant-diary-go-sql/
├── 📁 backend/
│   ├── 📁 controllers/      # API route handlers
│   ├── 📁 models/          # Data models
│   ├── 📁 services/        # Business logic
│   ├── 📁 database/        # DB connection & migrations
│   ├── 📁 uploads/         # File storage
│   ├── 📄 main.go          # Application entry point
│   └── 📄 go.mod           # Go dependencies
├── 📁 frontend/
│   ├── 📁 src/
│   │   ├── 📁 components/  # Vue components
│   │   ├── 📁 views/       # Page components
│   │   ├── 📁 services/    # API calls
│   │   ├── 📁 assets/      # Static files
│   │   └── 📄 main.js      # Vue app entry
│   ├── 📄 package.json     # Node dependencies
│   └── 📄 vite.config.js   # Build configuration
├── 📄 docker-compose.yml   # Docker setup
├── 📄 README.md           # This file
└── 📄 .env.example        # Environment template
```

---

## 🛡️ Environment Configuration

Create a `.env` file in the root directory:

```bash
# Database Configuration
DB_HOST=localhost
DB_PORT=5432
DB_USER=plantdiary
DB_PASSWORD=your_password
DB_NAME=plant_diary

# Application Settings
APP_PORT=8080
APP_ENV=development
JWT_SECRET=your_jwt_secret_here

# File Upload Settings
MAX_UPLOAD_SIZE=10MB
UPLOAD_PATH=./uploads

# Frontend URL (for CORS)
FRONTEND_URL=http://localhost:3000
```

---

## 🔧 Development

### 🏃‍♂️ **Running in Development**

```bash
# Terminal 1: Backend
cd backend
go run main.go

# Terminal 2: Frontend  
cd frontend
npm run dev

# Terminal 3: Database (if using local setup)
# SQLite: No additional setup needed
# PostgreSQL: 
sudo service postgresql start
```

### 🧪 **Testing**

```bash
# Backend tests
cd backend
go test ./...

# Frontend tests
cd frontend
npm run test

# Integration tests
npm run test:e2e
```

### 🏗️ **Building for Production**

```bash
# Build frontend
cd frontend
npm run build

# Build backend
cd backend
go build -o plant-diary main.go

# Deploy files
./plant-diary
```

---

## 🤝 Contributing

We love contributions! Here's how you can help make Plant Diary even better:

### 🌟 **Ways to Contribute**

- 🐛 **Bug Reports**: Found a bug? Open an issue!
- ✨ **Feature Requests**: Have an idea? We'd love to hear it!
- 📝 **Documentation**: Help improve our docs
- 🔧 **Code**: Submit pull requests for fixes and features

### 📝 **Development Workflow**

```bash
# 1. Fork the repository
git fork https://github.com/NK-GO/plant-diary-go-sql

# 2. Create a feature branch
git checkout -b feature/awesome-new-feature

# 3. Make your changes and commit
git commit -m "✨ Add awesome new feature"

# 4. Push and create pull request
git push origin feature/awesome-new-feature
```

### 🎯 **Contribution Areas**

- 🌱 **Plant Database**: Expand plant species information
- 📱 **Mobile Support**: Improve responsive design
- 🔍 **Search & Filter**: Enhanced plant discovery
- 📊 **Analytics**: Growth tracking and insights
- 🔔 **Notifications**: Watering and care reminders
- 🌍 **Internationalization**: Multi-language support

---

## 🔍 Features Roadmap

### 🎯 **Version 2.1 (Coming Soon)**
- [ ] 🔍 Advanced plant search and filtering
- [ ] 📅 Watering schedule reminders
- [ ] 📈 Growth analytics dashboard
- [ ] 📱 PWA support for mobile
- [ ] 🌙 Dark mode theme

### 🚀 **Version 3.0 (Future)**
- [ ] 🤖 AI-powered plant identification
- [ ] 🌐 Social features and plant sharing
- [ ] ☁️ Cloud sync and backup
- [ ] 📊 Advanced reporting and insights
- [ ] 🛒 Plant marketplace integration

---

## 📚 Resources & Links

### 📖 **Documentation**
- [Echo Framework Guide](https://echo.labstack.com/guide/)
- [Vue.js Documentation](https://vuejs.org/guide/)
- [Go SQL Tutorial](https://golang.org/doc/tutorial/database-access)

### 🔗 **Useful Links**
- [Go Download](https://golang.org/dl/)
- [Node.js Download](https://nodejs.org/)
- [Git Installation](https://git-scm.com/downloads)

### 🎓 **Learning Resources**
- [Go by Example](https://gobyexample.com/)
- [Vue.js Examples](https://vuejsexamples.com/)
- [REST API Best Practices](https://restfulapi.net/)

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License - feel free to use this project for personal or commercial purposes!
```

---

## 🙏 Acknowledgments

- 🌱 **Plant Community**: For inspiration and plant care knowledge
- ⚡ **Echo Team**: For the amazing Go web framework
- 🎨 **Vue.js Team**: For the reactive frontend framework
- 👥 **Contributors**: Everyone who helps make this project better

---

<div align="center">

## 🌿 Happy Gardening! 🌱

**Made with 💚 for plant lovers everywhere**

[![GitHub](https://img.shields.io/badge/GitHub-NK--GO-green?style=for-the-badge&logo=github)](https://github.com/NK-GO)
[![Stars](https://img.shields.io/github/stars/NK-GO/plant-diary-go-sql?style=for-the-badge&color=green)](https://github.com/NK-GO/plant-diary-go-sql/stargazers)

*"The best time to plant a tree was 20 years ago. The second best time is now."*

---

### 📧 Questions or Suggestions?

Open an issue or start a discussion - we're here to help! 🌟

</div>
