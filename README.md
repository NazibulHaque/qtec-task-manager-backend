🚀 TaskFlow — Full Stack Task Management System

A clean, modern task management system built with Laravel (REST API) and React (SPA).
Developed as part of the Qtec Solution Limited technical assessment.

🌐 Live Demo
Frontend: https://qtec-task-manager.vercel.app
Backend API: https://qtec-task-manager-backend.vercel.app

📁 Project Structure
task-manager/
├── backend/                          # Laravel 11 REST API
│   ├── app/
│   │   ├── Http/
│   │   │   ├── Controllers/
│   │   │   │   └── TaskController.php    # CRUD with search & filter
│   │   │   ├── Requests/
│   │   │   │   └── TaskRequest.php       # Form validation
│   │   │   └── Resources/
│   │   │       └── TaskResource.php      # JSON response shaping
│   │   └── Models/
│   │       └── Task.php                  # Eloquent model with scopes
│   ├── database/
│   │   ├── migrations/                   # Task schema
│   │   ├── factories/                    # TaskFactory for testing
│   │   └── seeders/                      # Sample data seeder
│   ├── routes/
│   │   └── api.php                       # API routes
│   └── tests/
│       ├── Feature/
│       │   └── TaskApiTest.php           # Feature tests
│       └── Unit/
│           └── TaskModelTest.php         # Unit tests
└── frontend/                         # React Application
    ├── src/
    │   ├── components/
    │   │   ├── ui/                       # Reusable UI components
    │   │   │   ├── Button.jsx
    │   │   │   ├── Input.jsx
    │   │   │   └── Badge.jsx
    │   │   ├── TaskCard.jsx
    │   │   ├── TaskForm.jsx
    │   │   ├── TaskBoard.jsx
    │   │   ├── SearchBar.jsx
    │   │   └── FilterDropdown.jsx
    │   ├── services/
    │   │   └── taskService.js            # Axios API layer
    │   ├── hooks/
    │   │   ├── useDebounce.js
    │   │   └── useTasks.js
    │   └── pages/
    │       └── Home.jsx
    └── .env                              # API base URL config

🛠️ Technologies Used
🔧 Backend
Technology	Purpose
Laravel 11	REST API framework
PHP 8.2	Backend language
MySQL	Production database
SQLite	Local development
API Resources	JSON formatting
Form Requests	Validation
PHPUnit	Testing
🎨 Frontend
Technology	Purpose
React 18	UI framework
Vite	Build tool
Tailwind CSS	Styling
Axios	API requests
Google Fonts (Syne + DM Sans)	Typography
⚙️ Setup Instructions


📌 Prerequisites
PHP 8.2+
Composer
Node.js 18+
npm
MySQL or SQLite


🔙 Backend Setup
# Navigate to backend
cd task-manager/backend

# Install dependencies
composer install

# Copy environment file
cp .env.example .env

# Generate app key
php artisan key:generate
Configure Database

SQLite (Recommended for quick setup):

DB_CONNECTION=sqlite
touch database/database.sqlite

MySQL:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=task_manager
DB_USERNAME=root
DB_PASSWORD=your_password
# Run migrations and seed data
php artisan migrate --seed

# Start server
php artisan serve
🔜 Frontend Setup
# Navigate to frontend
cd task-manager/frontend

# Install dependencies
npm install

Create .env file:

VITE_API_BASE_URL=http://127.0.0.1:8000/api
# Start development server
npm run dev
🧪 Running Tests
cd task-manager/backend

# Run all tests
php artisan test

# Feature tests
php artisan test --testsuite=Feature

# Unit tests
php artisan test --testsuite=Unit


🌐 API Endpoints
Method	Endpoint	Description
GET	/api/tasks	Get all tasks (search & filter supported)
POST	/api/tasks	Create task
GET	/api/tasks/{id}	Get single task
PUT	/api/tasks/{id}	Update task
DELETE	/api/tasks/{id}	Delete task


🔍 Query Parameters
Parameter	Description
search	Search by title/description
status	pending, in_progress, completed
priority	low, medium, high
📦 Example Response
{
  "data": [
    {
      "id": 1,
      "title": "Build task manager frontend",
      "description": "React SPA with kanban board",
      "status": "in_progress",
      "priority": "high",
      "due_date": "2026-04-22",
      "created_at": "2026-04-19 10:00:00"
    }
  ],
  "stats": {
    "total": 15,
    "pending": 6,
    "in_progress": 5,
    "completed": 4
  }
}

✅ Features
📌 Kanban Board (Pending / In Progress / Completed)
➕ Create Tasks
✏️ Edit Tasks
❌ Delete Tasks
🔍 Debounced Search
🎯 Filter by Status & Priority
📊 Live Stats Dashboard
⚠️ Overdue Indicator
📱 Fully Responsive UI
🌙 Modern Dark Theme
🧪 Testing Approach
🔹 Feature Tests (TaskApiTest.php)
List tasks with correct structure
Create task validation
Update & delete functionality
Search & filtering
🔹 Unit Tests (TaskModelTest.php)
Model fillable fields
Query scopes (pending, completed, search)
🔹 Strategy
RefreshDatabase for isolation
SQLite in-memory testing
Factory-based test data
Covers success + failure cases
💡 Decisions & Assumptions
🏗️ Architecture
Monorepo with separated frontend & backend
RESTful API design
React SPA for smooth UX
⚙️ Backend
API Resources for consistent responses
Form Requests for validation
Model Scopes for clean queries
SQLite (dev) + MySQL (prod)
🎨 Frontend
Custom hooks (useTasks, useDebounce)
Kanban UI for clarity
Dark modern UI
Modal-based editing
📌 Assumptions
No authentication required
Single-user system
No project/category relation
Optional due date


👨‍💻 Author
Nazibul Haque Shuvo
Full Stack Laravel Developer

🔗 GitHub: https://github.com/NazibulHaque
