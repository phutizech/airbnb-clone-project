# airbnb-clone-project
AirBnB Clone Project - Full Stack Web Application

## Overview
This project is a full-stack web application that replicates the core functionality of AirBnB. It includes user authentication, property listings, booking system, and review features.

## Project Goals
- Build a complete full-stack application from scratch
- Implement user authentication and authorization
- Create a responsive and intuitive user interface
- Develop a robust backend with proper database management
- Learn and apply modern web development technologies

## Tech Stack(Brief overview)
- **Frontend**: React.js, HTML5, CSS3, JavaScript (ES6+)
- **Backend**: Node.js, Express.js
- **Database**: MongoDB/Mongoose
- **Authentication**: JWT (JSON Web Tokens)
- **Deployment**: Heroku/Vercel/Netlify
- **Version Control**: Git/GitHub
- **Additional Tools**: Postman, VS Code

## Features
- User registration and login
- Property listing and search
- Booking system
- Reviews and ratings
- Responsive design

## Team Roles

| Role | Responsibilities |
|------|-----------------|
| **Project Manager** | Oversees project planning, coordinates team efforts, manages timelines, and communicates with stakeholders |
| **Frontend Developer** | Implements UI components, ensures responsive design, and optimizes frontend performance |
| **Backend Developer** | Develops server-side logic, creates RESTful APIs, and implements authentication systems |
| **Database Administrator** | Designs database schema, manages MongoDB, and ensures data integrity |
| **Full Stack Developer** | Works on both frontend and backend components and ensures seamless integration |
| **DevOps Engineer** | Manages deployment pipelines, configures CI/CD, and handles server infrastructure |
| **QA Engineer** | Develops test plans, performs testing, and ensures code quality |
| **UX/UI Designer** | Creates user interface designs and ensures user-friendly experience |
| **Security Specialist** | Implements security best practices and ensures data protection compliance |

## Technology Stack

| Technology | Purpose in Project |
|------------|-------------------|
| **React.js** | Building dynamic and responsive user interface components |
| **Node.js** | Server-side JavaScript runtime for backend operations |
| **Express.js** | Web application framework for building RESTful APIs |
| **MongoDB** | NoSQL database for storing application data with scalability |
| **Mongoose** | ODM library for MongoDB data modeling and validation |
| **JWT** | Secure user authentication and authorization |
| **HTML5/CSS3** | Structure and styling of web pages |
| **Git/GitHub** | Version control and collaboration platform |

## Database Design

### Key Entities

#### 1. Users
**Important Fields:**
- `_id`: Unique identifier (ObjectId)
- `email`: Unique email address for authentication
- `password`: Hashed password for security
- `firstName` & `lastName`: User's full name
- `role`: User type (host, guest, or admin)

**Relationships:**
- A User can have multiple Properties (as a host)
- A User can make multiple Bookings (as a guest)
- A User can write multiple Reviews
- A User can receive multiple Reviews (as a host)

#### 2. Properties
**Important Fields:**
- `_id`: Unique identifier (ObjectId)
- `title`: Property name/title
- `description`: Detailed property description
- `pricePerNight`: Rental price per night
- `hostId`: Reference to User who owns the property
- `location`: Address and geographic coordinates

**Relationships:**
- A Property belongs to one User (host)
- A Property can have multiple Bookings
- A Property can have multiple Reviews
- A Property can have multiple Amenities

#### 3. Bookings
**Important Fields:**
- `_id`: Unique identifier (ObjectId)
- `propertyId`: Reference to the booked Property
- `guestId`: Reference to User making the booking
- `checkInDate`: Start date of booking
- `checkOutDate`: End date of booking
- `totalPrice`: Calculated total cost
- `status`: Booking status (pending, confirmed, cancelled)

**Relationships:**
- A Booking belongs to one Property
- A Booking belongs to one User (guest)
- A Booking can have one associated Payment
- A Booking can have one Review

#### 4. Reviews
**Important Fields:**
- `_id`: Unique identifier (ObjectId)
- `propertyId`: Reference to the reviewed Property
- `authorId`: Reference to User writing the review
- `rating`: Numerical rating (1-5 stars)
- `comment`: Text review content
- `createdAt`: Timestamp of review creation

**Relationships:**
- A Review belongs to one Property
- A Review belongs to one User (author)
- A Review can be associated with one Booking

#### 5. Payments
**Important Fields:**
- `_id`: Unique identifier (ObjectId)
- `bookingId`: Reference to associated Booking
- `amount`: Payment amount
- `paymentMethod`: Credit card, PayPal, etc.
- `status`: Payment status (pending, completed, failed)
- `transactionId`: Unique transaction identifier

**Relationships:**
- A Payment belongs to one Booking
- A Payment is processed for one User (guest)

#### 6. Amenities (Additional Entity)
**Important Fields:**
- `_id`: Unique identifier (ObjectId)
- `name`: Amenity name (WiFi, Pool, Kitchen, etc.)
- `icon`: Visual representation icon

**Relationships:**
- Many Properties can have many Amenities (many-to-many relationship)

### Database Relationships Summary
- **One-to-Many**: User → Properties, User → Bookings, User → Reviews
- **One-to-Many**: Property → Bookings, Property → Reviews
- **One-to-One**: Booking → Payment, Booking → Review
- **Many-to-Many**: Properties ↔ Amenities

## Getting Started
(Instructions will be added as the project progresses)
