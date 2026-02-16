# HouseHunt-Finding Your Perfect Rental Home
 RentHub - Property Rental Management Platform

A full-stack web application for managing property rentals and bookings. Users can browse properties, book rentals, and property owners can list their properties.

## 🌟 Features

- **User Authentication**: Secure login/registration with JWT tokens
- **Multi-Role System**: Admin, Owner, and Renter roles
- **Property Management**: Owners can add, update, and delete properties
- **Property Browsing**: Renters can filter and search properties by type, location, and ad type
- **Booking System**: Renters can book properties; owners can manage bookings
- **Admin Dashboard**: Admins can manage users, properties, and bookings
- **Responsive Design**: Mobile-friendly UI with Bootstrap and Material-UI
- **Image Upload**: Support for multiple property images with file uploads

## 🛠️ Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM (Object Data Modeling)
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Multer** - File upload handling
- **Nodemon** - Development server auto-reload

### Frontend
- **React** - UI library
- **React Router** - Client-side routing
- **Bootstrap** - CSS framework
- **Material-UI** - Component library
- **Ant Design** - UI components
- **Axios** - HTTP client

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MongoDB** (local or cloud instance like MongoDB Atlas)

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd House-hunt-finding-your-perfect-rental-home-main
```

### 2. Backend Setup

Navigate to the backend directory:
```bash
cd backend
```

Install dependencies:
```bash
npm install
```

Create a `.env` file in the backend directory:
```env
MONGO_DB=mongodb://localhost:27017/project
JWT_KEY=your_jwt_secret_key_12345
```

Start the backend server:
```bash
npm start
```

The server will run on `http://localhost:8001`

### 3. Frontend Setup

Navigate to the frontend directory:
```bash
cd ../frontend
```

Install dependencies:
```bash
npm install
```

Start the development server:
```bash
npm start
```

The application will run on `http://localhost:3000` or `http://localhost:3001`

## 📁 Project Structure

```
House-hunt-finding-your-perfect-rental-home-main/
├── backend/
│   ├── config/
│   │   └── connect.js           # MongoDB connection
│   ├── controllers/
│   │   ├── adminController.js   # Admin operations
│   │   ├── ownerController.js   # Owner operations
│   │   └── userController.js    # User/Renter operations
│   ├── middlewares/
│   │   └── authMiddlware.js     # JWT authentication
│   ├── routes/
│   │   ├── adminRoutes.js
│   │   ├── ownerRoutes.js
│   │   └── userRoutes.js
│   ├── schemas/
│   │   ├── userModel.js         # User schema
│   │   ├── propertyModel.js     # Property schema
│   │   └── bookingModel.js      # Booking schema
│   ├── uploads/                 # Property images
│   ├── index.js                 # Server entry point
│   └── package.json
│
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── modules/
│   │   │   ├── admin/           # Admin pages
│   │   │   ├── common/          # Shared pages (Login, Register, Home)
│   │   │   └── user/
│   │   │       ├── Owner/       # Owner-specific pages
│   │   │       └── renter/      # Renter-specific pages
│   │   ├── App.js
│   │   ├── App.css
│   │   └── index.js
│   ├── package.json
│   └── README.md
│
└── README.md
```

## 🔑 API Endpoints

### User Routes
- `POST /api/user/register` - Register new user
- `POST /api/user/login` - User login
- `POST /api/user/forgotpassword` - Password reset
- `GET /api/user/getAllProperties` - Get all properties
- `POST /api/user/getuserdata` - Get user data (protected)
- `POST /api/user/bookinghandle/:propertyid` - Create booking (protected)
- `GET /api/user/getallbookings` - Get user bookings (protected)

### Owner Routes
- `POST /api/owner/postproperty` - Add new property (protected)
- `GET /api/owner/getAllOwnerProperties` - Get owner's properties (protected)
- `DELETE /api/owner/deleteProperty/:propertyid` - Delete property (protected)
- `PUT /api/owner/updateProperty/:propertyid` - Update property (protected)
- `GET /api/owner/getAllBookings` - Get property bookings (protected)
- `POST /api/owner/handleBookingStatus` - Update booking status (protected)

### Admin Routes
- `GET /api/admin/getAllUsers` - Get all users
- `GET /api/admin/getallproperties` - Get all properties (protected)
- `POST /api/admin/handleStatus` - Update user status (protected)
- `GET /api/admin/getallbookings` - Get all bookings (protected)

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication:
- Tokens are stored in localStorage after login
- Protected routes require the `Authorization: Bearer <token>` header
- Tokens expire after 1 day

## 👥 User Roles

1. **Admin**: Can manage all users, properties, and bookings
2. **Owner**: Can add, update, and manage their properties; view booking requests
3. **Renter**: Can browse, filter, and book properties

## 📝 Environment Variables

### Backend (.env)
```
MONGO_DB=mongodb://localhost:27017/project
JWT_KEY=your_secure_jwt_key
```

## 🐛 Troubleshooting

### MongoDB Connection Issues
- Ensure MongoDB is running locally or provide a valid Atlas connection string
- Update `MONGO_DB` in `.env`

### Port Already in Use
- Port 8001 (backend) or 3000/3001 (frontend) might be in use
- Kill the process: `taskkill /PID <PID> /F` (Windows)

### JWT Token Errors
- Ensure `JWT_KEY` is set in `.env`
- Restart the backend server after updating `.env`

## 🚴 Running Tests

To run backend tests:
```bash
cd backend
npm test
```

## 📦 Build for Production

### Frontend Build
```bash
cd frontend
npm run build
```

This creates an optimized production build in the `build` folder.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**Your Name** - [GitHub Profile](https://github.com/yourprofile)

## 📧 Support

For support, email support@renthub.com or open an issue on GitHub.

## 🗺️ Roadmap

- [ ] Email notifications for bookings
- [ ] Payment integration (Stripe/PayPal)
- [ ] Property reviews and ratings
- [ ] Advanced search filters
- [ ] Mobile app (React Native)
- [ ] Real-time chat between owners and renters
- [ ] Property analytics dashboard

---

**Happy coding! 🚀**
