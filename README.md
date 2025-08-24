# AirBnB Clone Project

## Overview
The AirBnB Clone project is a step-by-step initiative to build a simplified version of the AirBnB web application. The goal is to learn and practice **full-stack development concepts** including backend, frontend, database management, and deployment.

## Project Goals
- Understand and implement object-oriented programming (OOP) concepts.
- Build a command-line interface for data management.
- Develop a RESTful API for handling application data.
- Design and integrate a database for persistence.
- Create a dynamic front-end interface for users.
- Deploy the application to a production environment.

## Tech Stack
- **Programming Language:** Python  
- **Frameworks:** Flask (backend), possibly React or vanilla HTML/CSS/JS (frontend)  
- **Database:** MySQL / SQLite  
- **Version Control:** Git & GitHub  
- **Deployment:** Docker / Heroku / AWS (depending on stage)  

---

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/Otavie/airbnb-clone-project.git
   cd airbnb-clone-project

---

## Team Roles

In order to build the AirBnB Clone project efficiently, the team is divided into specialized roles. Each role ensures smooth progress, quality delivery, and collaboration.

### 1. Project Manager (PM)
- Oversees the project timeline, deliverables, and team coordination.
- Ensures that goals, deadlines, and milestones are met.
- Acts as the main communicator between the team and stakeholders.

### 2. Backend Developer
- Responsible for implementing the application logic and APIs using Python (Flask/Django).
- Manages data processing, authentication, and communication between the front end and the database.
- Ensures that the system is scalable and secure.

### 3. Frontend Developer
- Builds the user interface using HTML, CSS, JavaScript (and optionally React).
- Ensures that the design is responsive, interactive, and user-friendly.
- Integrates front-end components with backend services.

### 4. Database Administrator (DBA)
- Designs and manages the project database (MySQL/SQLite).
- Ensures data consistency, security, and optimization.
- Works closely with backend developers to implement database queries and migrations.

### 5. DevOps Engineer
- Handles deployment, version control, and CI/CD pipelines.
- Manages server infrastructure, Docker, and cloud hosting (e.g., AWS/Heroku).
- Ensures reliability, performance monitoring, and scalability.

### 6. QA Engineer (Tester)
- Creates test cases and performs manual/automated testing.
- Ensures the application is free from bugs and meets requirements.
- Works with developers to fix and re-test issues.

### 7. UI/UX Designer
- Designs wireframes, prototypes, and user flows.
- Focuses on accessibility, ease of navigation, and visual appeal.
- Collaborates with frontend developers to bring designs to life.

---

## Technology Stack

The AirBnB Clone project uses a modern technology stack that supports **scalability**, **maintainability**, and **ease of collaboration**. Each technology serves a specific purpose in the system architecture.

### 1. Python
- The primary programming language for implementing backend logic.
- Provides flexibility, readability, and a rich ecosystem of libraries.

### 2. Django / Flask
- **Django**: A high-level web framework that enables rapid development and clean design patterns (used for building RESTful APIs, authentication, and admin dashboards).
- **Flask**: A lightweight alternative used for microservices and modular development when more flexibility is needed.

### 3. PostgreSQL / MySQL
- Relational database systems for storing persistent data such as users, bookings, property listings, and transactions.
- Ensures data integrity, indexing, and optimized queries.

### 4. GraphQL (optional extension)
- Provides a flexible query language for APIs.
- Allows frontend clients to request exactly the data they need, reducing over-fetching and under-fetching.

### 5. HTML, CSS, JavaScript
- **HTML**: Defines the structure of the frontend.
- **CSS**: Styles and formats the interface for a visually appealing design.
- **JavaScript**: Adds interactivity, client-side validation, and dynamic rendering.

### 6. React (optional enhancement)
- A frontend JavaScript library for building dynamic, component-based user interfaces.
- Improves responsiveness and enhances the user experience.

### 7. Git & GitHub
- **Git**: Version control system to track code changes and enable collaboration.
- **GitHub**: A remote repository for hosting code, managing issues, and collaborating with teammates.

### 8. Docker
- Containerization platform to package and deploy applications consistently across environments.
- Ensures portability and eliminates "works on my machine" issues.

### 9. Heroku / AWS (Deployment)
- **Heroku**: A platform-as-a-service (PaaS) for simple deployment and scaling.
- **AWS**: Provides cloud infrastructure for high scalability, load balancing, and production readiness.

---

## Database Design

The AirBnB Clone project relies on a relational database structure to manage users, properties, bookings, reviews, and payments. Below are the core entities, their fields, and relationships.

### 1. Users
- **Fields:**
  - `id` (Primary Key)
  - `name` (full name of the user)
  - `email` (unique identifier for login)
  - `password` (hashed for security)
  - `role` (guest, host, or admin)
- **Relationships:**
  - A user can list multiple properties (Host).
  - A user can make multiple bookings (Guest).
  - A user can leave multiple reviews.

---

### 2. Properties
- **Fields:**
  - `id` (Primary Key)
  - `title` (property name/listing title)
  - `description` (details about the property)
  - `location` (address/city)
  - `price_per_night`
  - `owner_id` (Foreign Key → Users.id)
- **Relationships:**
  - A property belongs to a user (the host).
  - A property can have multiple bookings.
  - A property can receive multiple reviews.

---

### 3. Bookings
- **Fields:**
  - `id` (Primary Key)
  - `user_id` (Foreign Key → Users.id)
  - `property_id` (Foreign Key → Properties.id)
  - `check_in_date`
  - `check_out_date`
  - `status` (pending, confirmed, cancelled)
- **Relationships:**
  - A booking belongs to a user (the guest).
  - A booking is tied to one property.
  - A booking can have one associated payment.

---

### 4. Reviews
- **Fields:**
  - `id` (Primary Key)
  - `user_id` (Foreign Key → Users.id)
  - `property_id` (Foreign Key → Properties.id)
  - `rating` (1–5 stars)
  - `comment`
  - `created_at`
- **Relationships:**
  - A review belongs to a user.
  - A review belongs to a property.

---

### 5. Payments
- **Fields:**
  - `id` (Primary Key)
  - `booking_id` (Foreign Key → Bookings.id)
  - `amount`
  - `payment_method` (card, PayPal, etc.)
  - `status` (pending, successful, failed)
  - `transaction_date`
- **Relationships:**
  - A payment is linked to a booking.
  - A booking can only have one payment record.

---

### Entity Relationships (Summary)
- A **User** can own multiple **Properties**.
- A **User** can make multiple **Bookings**.
- A **Property** can have multiple **Bookings** and **Reviews**.
- A **Booking** belongs to one **User** and one **Property**, and is linked to one **Payment**.
- A **Review** links a **User** (guest) with a **Property** (host listing).

---

## Feature Breakdown

The AirBnB Clone project is divided into several core features that replicate the essential functionality of the real AirBnB platform. Each feature is designed to provide value to users while ensuring smooth interactions between guests, hosts, and the system.

### 1. User Management
- Handles user registration, authentication (login/logout), and profile management.
- Supports different roles (guest, host, admin) with role-based permissions.
- Ensures data security through password hashing and secure session handling.

### 2. Property Management
- Allows hosts to create, update, and delete property listings.
- Each property contains details such as title, description, location, price per night, and availability.
- Provides search and filtering options so guests can easily discover properties.

### 3. Booking System
- Enables guests to book available properties for specific dates.
- Handles booking requests, confirmations, cancellations, and status tracking.
- Ensures that booking conflicts are avoided by maintaining property availability.

### 4. Review & Rating System
- Guests can leave reviews and ratings for properties after their stay.
- Reviews include a star rating (1–5) and optional written feedback.
- Helps future guests make informed decisions and allows hosts to build credibility.

### 5. Payment System
- Provides a secure way for guests to make payments for their bookings.
- Supports multiple payment methods (credit/debit cards, PayPal, etc.).
- Tracks payment status (pending, successful, failed) and links each payment to a booking.

### 6. Search & Filtering
- Guests can search for properties by location, date, price range, and other criteria.
- Implements filtering and sorting to enhance the user experience.
- Ensures that users can quickly find the most relevant listings.

### 7. Admin Dashboard
- Allows administrators to monitor and manage the platform.
- Provides tools for managing users, properties, bookings, and reported issues.
- Ensures the platform remains safe, reliable, and efficient for all users.

---
