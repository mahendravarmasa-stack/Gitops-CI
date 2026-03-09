# 📝 ToDo Application

A modern, full-stack ToDo application built with React, FastAPI, and MongoDB. This application provides a clean and intuitive interface for managing your daily tasks.

## 🚀 Features

- **Create, Read, Update, Delete** todo items
- **Mark tasks as complete/incomplete**
- **Add descriptions** to your todos
- **Real-time updates** with modern UI
- **Responsive design** that works on all devices
- **RESTful API** with FastAPI
- **MongoDB** for data persistence

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   React App     │────│   FastAPI       │────│   MongoDB       │
│   (Frontend)    │    │   (Backend)     │    │   (Database)   │
│   Port: 3000    │    │   Port: 8000    │    │   Port: 27017   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 🛠️ Tech Stack

### Frontend
- **React 18** - Modern UI library
- **Axios** - HTTP client for API calls
- **CSS3** - Modern styling with gradients and animations

### Backend
- **FastAPI** - High-performance Python web framework
- **Pydantic** - Data validation and serialization
- **Motor** - Async MongoDB driver
- **Uvicorn** - ASGI server

### Database
- **MongoDB** - NoSQL document database

## 🚀 Quick Start

### Option 1: Using Docker (Recommended)

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd todo-app
   ```

2. **Start all services with Docker Compose**
   ```bash
   docker-compose up --build
   ```

3. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8000
   - API Documentation: http://localhost:8000/docs

### Option 2: Manual Setup

#### Prerequisites
- Node.js 18+ and npm
- Python 3.11+
- MongoDB

#### Backend Setup
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

#### Frontend Setup
```bash
cd frontend
npm install
npm start
```

#### Database Setup
Make sure MongoDB is running on `localhost:27017`

## 📚 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/todos` | Get all todos |
| POST | `/todos` | Create a new todo |
| GET | `/todos/{id}` | Get a specific todo |
| PUT | `/todos/{id}` | Update a todo |
| DELETE | `/todos/{id}` | Delete a todo |

### Example API Usage

```bash
# Get all todos
curl http://localhost:8000/todos

# Create a new todo
curl -X POST http://localhost:8000/todos \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn FastAPI", "description": "Study FastAPI documentation"}'

# Update a todo
curl -X PUT http://localhost:8000/todos/{id} \
  -H "Content-Type: application/json" \
  -d '{"completed": true}'
```

## 🎨 UI Features

- **Modern Design**: Clean, gradient-based interface
- **Responsive Layout**: Works on desktop, tablet, and mobile
- **Interactive Elements**: Hover effects and smooth transitions
- **Status Indicators**: Visual feedback for todo states
- **Form Validation**: Client-side validation for better UX

## 🔧 Development

### Project Structure
```
todo-app/
├── backend/
│   ├── main.py              # FastAPI application
│   ├── requirements.txt     # Python dependencies
│   └── Dockerfile          # Backend container config
├── frontend/
│   ├── src/
│   │   ├── App.js          # Main React component
│   │   ├── index.js        # React entry point
│   │   └── index.css       # Global styles
│   ├── package.json        # Node.js dependencies
│   └── Dockerfile          # Frontend container config
├── docker-compose.yml      # Multi-container setup
└── README.md              # This file
```

### Environment Variables

Create a `.env` file in the backend directory:
```
MONGODB_URL=mongodb://localhost:27017
```

## 🐳 Docker Commands

```bash
# Build and start all services
docker-compose up --build

# Start services in background
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down

# Remove volumes (clean database)
docker-compose down -v
```

## 🧪 Testing

### Backend Testing
```bash
cd backend
python -m pytest
```

### Frontend Testing
```bash
cd frontend
npm test
```

## 📝 Todo Data Model

```json
{
  "id": "string",
  "title": "string",
  "description": "string",
  "completed": "boolean",
  "created_at": "datetime"
}
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🆘 Troubleshooting

### Common Issues

1. **Port conflicts**: Make sure ports 3000, 8000, and 27017 are available
2. **MongoDB connection**: Ensure MongoDB is running and accessible
3. **CORS errors**: Check that the backend allows requests from the frontend
4. **Docker issues**: Try rebuilding containers with `docker-compose up --build`

### Getting Help

- Check the API documentation at http://localhost:8000/docs
- Review the browser console for frontend errors
- Check Docker logs: `docker-compose logs [service-name]`

---

**Happy coding! 🎉**
