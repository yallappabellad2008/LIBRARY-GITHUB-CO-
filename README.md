# LIBRARY-GITHUB-CO-
# 📚 Library Management System - Full Stack Implementation

A professional Django REST Framework-based Library Management System with a beautiful, responsive web interface for managing books.
<img width="1533" height="787" alt="WhatsApp Image 2026-05-18 at 10 48 09 AM" src="https://github.com/user-attachments/assets/a842d4d3-3192-49ae-894c-57d39060d5b1" />


---

## 🌐 What is an API?

### Definition
An **API (Application Programming Interface)** is a set of rules and protocols that allows different software applications to communicate with each other. It defines the methods and data formats that applications can use to request and exchange information.

### Key Characteristics
- **Interface**: A defined set of functions and procedures for accessing services
- **Communication Protocol**: Uses standard protocols (HTTP/HTTPS) for web APIs
- **Data Format**: Typically exchanges data in JSON or XML format
- **Stateless**: Each request contains all the information needed to process it
- **Reusable**: Can be consumed by multiple client applications

### How APIs Work
```
Client (Frontend)
      ↓ (HTTP Request)
    API Gateway
      ↓
  Server/Backend
      ↓ (Process Request)<img width="1533" height="787" alt="WhatsApp Image 2026-05-18 at 10 48 09 AM" src="https://github.com/user-attachments/assets/c40f0a77-a404-4342-9ff1-5a12cc338f1f" />

   Database
      ↓
  Server/Backend
      ↓ (HTTP Response)
    API Gateway
      ↓ (JSON Response)
Client (Receives Data)
```

---

## 💼 Real-World Applications of APIs

### 1. **E-Commerce Platforms**
   - Product catalogs and inventory management
   - Payment processing integration (Stripe, PayPal)
   - Order management and tracking
   - Customer reviews and ratings

### 2. **Social Media**
   - User authentication and profile management
   - Feed generation and content delivery
   - Messaging and notifications
   - Photo and video uploads

### 3. **Weather & Maps**
   - Real-time weather data
   - Geographic location services
   - Route planning and navigation
   - Traffic information

### 4. **Financial Services**
   - Banking transactions and account management
   - Stock market data and trading
   - Cryptocurrency exchanges
   - Lending and credit services

### 5. **Streaming Services**
   - Content delivery and recommendations
   - User preferences and watch history
   - Subscription management
   - Video encoding and streaming

### 6. **Travel & Booking**
   - Flight and hotel availability
   - Reservation systems
   - Payment processing
   - Itinerary management

### 7. **Healthcare**
   - Patient records management
   - Appointment scheduling
   - Prescription management
   - Telemedicine services

### 8. **IoT & Smart Devices**
   - Device communication and control
   - Sensor data collection
   - Remote monitoring
   - Firmware updates

---

## 📖 REST API Principles

This project implements a **RESTful API** which follows these principles:

| Principle | Description |
|-----------|-------------|
| **Resources** | Everything is a resource (books, users, etc.) identified by URLs |
| **HTTP Methods** | Uses standard methods: GET (read), POST (create), PUT (update), DELETE (delete) |
| **Stateless** | Each request is independent and contains all necessary information |
| **Status Codes** | Uses HTTP status codes (200, 201, 400, 404, 500) to indicate results |
| **JSON Format** | Data is exchanged in JSON format for readability and parsing |

---

## 🎯 Project Overview

## 🎯 Features Implemented

### Backend (Django REST Framework)

#### API Endpoints
- **GET** `/api/books/` - List all books (with pagination)
- **POST** `/api/books/` - Create a new book
- **GET** `/api/books/{id}/` - Retrieve specific book details
- **PUT** `/api/books/{id}/` - Full update of book details
- **PATCH** `/api/books/{id}/` - Partial update of book details
- **DELETE** `/api/books/{id}/` - Delete a book
- **POST** `/api/books/{id}/set_availability/` - Toggle book availability status

#### Custom Actions
- `available_books` - Filter to show only available books
- `unavailable_books` - Filter to show only unavailable books
- `set_availability` - Toggle the availability status of a book

#### Models
- **Book Model** with fields:
  - `title` - Book title (CharField, max 200 chars)
  - `author` - Author name (CharField, max 100 chars)
  - `isbn` - ISBN number (CharField, max 13, unique)
  - `published_year` - Year of publication (IntegerField)
  - `is_available` - Availability status (BooleanField, default: True)

### Frontend (HTML/CSS/JavaScript)

#### User Interface
- 📱 **Responsive Design** - Works on desktop, tablet, and mobile devices
- 🎨 **Modern Styling** - Beautiful gradient backgrounds and smooth animations
- ⚡ **Real-time Updates** - Instant feedback on all operations

#### Features
1. **Add Books** - Form to add new books to the library
2. **View Books** - Display all books in a beautiful card layout
3. **Edit Books** - Click edit to modify existing book details
4. **Delete Books** - Remove books from the collection
5. **Toggle Availability** - Mark books as available/unavailable for borrowing
6. **Filter Books** - Three filter options:
   - All Books
   - Available Only
   - Unavailable Only
7. **Real-time Notifications** - Success/error messages for all operations
8. **Form Validation** - Client-side validation for all inputs

#### Technical Features
- ✅ CSRF protection (automatic Django token handling)
- ✅ XSS prevention (HTML escaping)
- ✅ Clean, modern UI with professional styling
- ✅ Smooth animations and transitions
- ✅ Loading indicators during API calls
- ✅ Error handling with user-friendly messages

## 📁 Project Structure

```
library_project/
├── db.sqlite3                          # SQLite database
├── manage.py                           # Django management script
├── books/
│   ├── migrations/                     # Database migrations
│   ├── templates/
│   │   └── index.html                  # Main frontend interface
│   ├── __init__.py
│   ├── admin.py                        # Django admin configuration
│   ├── apps.py
│   ├── models.py                       # Book model definition
│   ├── serializers.py                  # DRF serializers (NEW)
│   ├── urls.py                         # Books app URL routing (NEW)
│   ├── views.py                        # DRF ViewSets (UPDATED)
│   └── tests.py
└── library_project/
    ├── __init__.py
    ├── asgi.py
    ├── settings.py                     # Project settings (UPDATED)
    ├── urls.py                         # Main URL configuration (UPDATED)
    └── wsgi.py
```

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Django 6.0.5
- Django REST Framework (already installed)

### Setup Instructions

1. **Run Migrations** (if not already done):
   ```bash
   python manage.py migrate
   ```

2. **Start Development Server**:
   ```bash
   python manage.py runserver
   ```

3. **Access the Application**:
   - Frontend: `http://127.0.0.1:8000/`
   - API Browsable Interface: `http://127.0.0.1:8000/api/books/`
   - Admin Panel: `http://127.0.0.1:8000/admin/`

## 📝 Usage Examples

### Using the Web Interface

1. **Add a Book**:
   - Fill in the book details (Title, Author, ISBN, Year)
   - Check "Available for Borrowing" if applicable
   - Click "Save Book"

2. **Edit a Book**:
   - Click the "Edit" button on any book card
   - The form will populate with the book's current details
   - Modify the information and click "Save Book"

3. **Delete a Book**:
   - Click the "Delete" button on any book card
   - Confirm the deletion in the popup

4. **Filter Books**:
   - Click "Available" to show only available books
   - Click "Unavailable" to show only unavailable books
   - Click "All Books" to show all books

5. **Toggle Availability**:
   - Click "Mark Unavailable" or "Mark Available" button
   - The status will update immediately

### Using the API with cURL

```bash
# Get all books
curl http://127.0.0.1:8000/api/books/

# Create a new book
curl -X POST http://127.0.0.1:8000/api/books/ \
  -H "Content-Type: application/json" \
  -d '{
    "title": "1984",
    "author": "George Orwell",
    "isbn": "9780451524935",
    "published_year": 1949,
    "is_available": true
  }'

# Get a specific book
curl http://127.0.0.1:8000/api/books/1/

# Update a book (full)
curl -X PUT http://127.0.0.1:8000/api/books/1/ \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Game of Thrones",
    "author": "George R. R. Martin",
    "isbn": "9780553103540",
    "published_year": 1996,
    "is_available": false
  }'

# Partial update
curl -X PATCH http://127.0.0.1:8000/api/books/1/ \
  -H "Content-Type: application/json" \
  -d '{"is_available": true}'

# Toggle availability
curl -X POST http://127.0.0.1:8000/api/books/1/set_availability/ \
  -H "Content-Type: application/json" \
  -d '{"is_available": false}'

# Delete a book
curl -X DELETE http://127.0.0.1:8000/api/books/1/
```

## 🎨 Design Features

### Color Scheme
- Primary Gradient: `#667eea` to `#764ba2` (Purple)
- Success: `#28a745` (Green)
- Error: `#dc3545` (Red)
- Warning: `#ffc107` (Yellow)
- Info: `#17a2b8` (Cyan)

### Responsive Breakpoints
- Desktop: Full 2-column layout (form + books list)
- Tablet/Mobile: Single column layout
- All components are mobile-optimized

## 📊 Database Schema

### Book Table
| Field | Type | Constraints |
|-------|------|-------------|
| id | Integer | Primary Key, Auto-increment |
| title | String(200) | Required, Indexed |
| author | String(100) | Required |
| isbn | String(13) | Required, Unique |
| published_year | Integer | Required |
| is_available | Boolean | Default: True |
| created_at | DateTime | Auto-generated |
| updated_at | DateTime | Auto-generated |

---

## 📡 HTTP Status Codes Reference

| Code | Name | Meaning | Example |
|------|------|---------|---------|
| **2xx - Success** | | | |
| 200 | OK | Request successful, data returned | GET /api/books/ |
| 201 | Created | Resource successfully created | POST /api/books/ |
| 204 | No Content | Request successful, no content to return | DELETE /api/books/1/ |
| **4xx - Client Error** | | | |
| 400 | Bad Request | Invalid request parameters | Missing required fields |
| 401 | Unauthorized | Authentication required | Missing API key |
| 403 | Forbidden | Authenticated but not authorized | No permission to delete |
| 404 | Not Found | Resource does not exist | GET /api/books/999/ |
| 409 | Conflict | Request conflicts with existing data | Duplicate ISBN |
| **5xx - Server Error** | | | |
| 500 | Internal Server Error | Unexpected server error | Database connection failed |
| 503 | Service Unavailable | Server temporarily unavailable | Maintenance mode |

---

## 🔐 API Best Practices

### 1. **Authentication & Authorization**
   - ✅ Use token-based authentication (API keys, JWT)
   - ✅ Validate all incoming requests
   - ✅ Implement role-based access control

### 2. **Data Validation**
   - ✅ Validate input data on the server side
   - ✅ Use appropriate data types and constraints
   - ✅ Return clear error messages

### 3. **Security**
   - ✅ Use HTTPS for all communications
   - ✅ Protect against SQL injection and XSS attacks
   - ✅ Implement CSRF protection
   - ✅ Sanitize all user inputs

### 4. **Rate Limiting**
   - ✅ Implement rate limiting to prevent abuse
   - ✅ Use throttling for heavy operations
   - ✅ Return 429 (Too Many Requests) when limit exceeded

### 5. **Documentation**
   - ✅ Maintain clear and up-to-date API documentation
   - ✅ Include request/response examples
   - ✅ Document all endpoints and parameters

### 6. **Versioning**
   - ✅ Use API versioning (v1/, v2/)
   - ✅ Support backwards compatibility
   - ✅ Deprecate old versions gradually

### 7. **Caching**
   - ✅ Implement caching strategies
   - ✅ Use ETags for conditional requests
   - ✅ Set appropriate cache headers

### 8. **Error Handling**
   - ✅ Return meaningful error messages
   - ✅ Use consistent error response format
   - ✅ Log errors for debugging

---

## 🛠️ Technology Stack

### Backend
- **Django 6.0.5** - Web framework
- **Django REST Framework (DRF)** - API framework
- **SQLite** - Database (development)
- **Python 3.8+** - Programming language

### Frontend
- **HTML5** - Markup
- **CSS3** - Styling
- **Vanilla JavaScript** - Interactivity (no external frameworks)
- **Fetch API** - HTTP client

### Development Tools
- **Git** - Version control
- **Virtual Environment** - Project isolation
- **pip** - Package manager

---

## 📚 API Request/Response Examples

### Example 1: Create a Book (POST)

**Request:**
```json
POST /api/books/
Content-Type: application/json

{
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "isbn": "9780743273565",
  "published_year": 1925,
  "is_available": true
}
```

**Response (201 Created):**
```json
{
  "id": 5,
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "isbn": "9780743273565",
  "published_year": 1925,
  "is_available": true
}
```

### Example 2: Get All Books (GET)

**Request:**
```
GET /api/books/?page=1
```

**Response (200 OK):**
```json
{
  "count": 10,
  "next": "http://127.0.0.1:8000/api/books/?page=2",
  "previous": null,
  "results": [
    {
      "id": 1,
      "title": "To Kill a Mockingbird",
      "author": "Harper Lee",
      "isbn": "9780061120084",
      "published_year": 1960,
      "is_available": true
    },
    ...
  ]
}
```

### Example 3: Update a Book (PATCH)

**Request:**
```json
PATCH /api/books/1/
Content-Type: application/json

{
  "is_available": false
}
```

**Response (200 OK):**
```json
{
  "id": 1,
  "title": "To Kill a Mockingbird",
  "author": "Harper Lee",
  "isbn": "9780061120084",
  "published_year": 1960,
  "is_available": false
}
```

### Example 4: Error Response (400 Bad Request)

**Request:**
```json
POST /api/books/
Content-Type: application/json

{
  "title": "Missing Fields"
}
```

**Response (400 Bad Request):**
```json
{
  "author": ["This field is required."],
  "isbn": ["This field is required."],
  "published_year": ["This field is required."]
}
```

---
| title | String(200) | Required |
| author | String(100) | Required |
| isbn | String(13) | Required, Unique |
| published_year | Integer | Required |
| is_available | Boolean | Default: True |

## 🔧 Configuration

### DRF Settings (settings.py)
```python
REST_FRAMEWORK = {
    'DEFAULT_PAGINATION_CLASS': 'rest_framework.pagination.PageNumberPagination',
    'PAGE_SIZE': 10,
    'DEFAULT_FILTER_BACKENDS': ['rest_framework.filters.SearchFilter', 'rest_framework.filters.OrderingFilter'],
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.AllowAny',
    ]
}
```

## 🛡️ Security Features

- ✅ CSRF Token Protection
- ✅ XSS Prevention (HTML escaping)
- ✅ SQL Injection Prevention (Django ORM)
- ✅ ALLOWED_HOSTS Configuration
- ✅ Debug Mode (set to False in production)

## 📚 Files Modified/Created

### New Files
- `books/serializers.py` - DRF Serializers for Book model
- `books/urls.py` - URL routing for books app
- `books/templates/index.html` - Frontend interface with embedded CSS/JS

### Modified Files
- `books/views.py` - Replaced with DRF ViewSet implementation
- `library_project/urls.py` - Updated to include books app URLs
- `library_project/settings.py` - Added REST Framework configuration

## 🚀 API Response Examples

### List Books Response
```json
{
  "count": 2,
  "next": null,
  "previous": null,
  "results": [
    {
      "id": 1,
      "title": "Game OF Thrones",
      "author": "Walter",
      "isbn": "9838788932878",
      "published_year": 2010,
      "is_available": true
    },
    {
      "id": 2,
      "title": "The Hobbit",
      "author": "J.R.R. Tolkien",
      "isbn": "9780547928227",
      "published_year": 1937,
      "is_available": false
    }
  ]
}
```

## 🧪 Testing

All CRUD operations have been tested and verified:
- ✅ Create - Add new books via form and API
- ✅ Read - Display books in list and detail views
- ✅ Update - Edit book information
- ✅ Delete - Remove books from database
- ✅ Filter - Show available/unavailable books
- ✅ Toggle - Change availability status

## 💡 Future Enhancements

Potential improvements for future versions:
- User authentication and authorization
- Book categories/genres
- Search functionality
- Book ratings and reviews
- Borrowing history and due dates
- Email notifications
- Advanced filtering and sorting
- Export to CSV/PDF
- Dark mode toggle

## 📞 Support

For issues or questions about this implementation:
1. Check the browser console for JavaScript errors
2. Check Django server logs for backend errors
3. Visit `http://127.0.0.1:8000/api/` for API documentation
4. Use the Django admin panel at `/admin/` for database inspection

---

**Developed as**: Junior Python Fullstack Developer (Django) Exercise
**Framework**: Django REST Framework
**Frontend**: Vanilla JavaScript (no external dependencies)
**Database**: SQLite
**Status**: ✅ Fully Functional
