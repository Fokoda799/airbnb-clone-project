# 🏠 Airbnb Clone Backend  

## 📖 Overview  

The **Airbnb Clone Backend** provides a **robust and scalable foundation** to power core features of Airbnb, including:  

- 👥 User authentication & profile management  
- 🏡 Property listings (create, update, search)  
- 📅 Booking system with check-in/check-out  
- 💳 Secure payment processing  
- ⭐ Reviews & ratings  
- ⚡ Optimized performance with caching & indexing  

### 🎯 Goals

- Deliver a robust booking platform with secure authentication and transactions.  
- Ensure smooth property management, bookings, and user interactions.  
- Optimize data handling with caching and indexing for high performance.  

### ⚙️ Tech Stack  

Built with modern tools for reliability and scalability:  
🐍 Django · 🔗 DRF · 🐘 PostgreSQL · 🔎 GraphQL · ⏳ Celery · ⚡ Redis · 🐳 Docker · 🤖 GitHub Actions

## 👥 Team Roles  

- 👨‍💻 **Backend Developer** – Builds APIs, business logic, and data models.  
- 🗄️ **Database Administrator** – Manages schema design & optimizations.  
- ⚙️ **DevOps Engineer** – Ensures smooth deployment, scaling, and monitoring.  
- 🧪 **QA Engineer** – Tests features and maintains system quality.

## ⚙️ Technology Stack  

This project uses a modern stack to ensure scalability, performance, and reliability:  

- 🐍 **Django** – A high-level Python web framework used to build the backend and handle core business logic.  
- 🔗 **Django REST Framework (DRF)** – Provides tools to create and manage RESTful APIs for users, properties, bookings, payments, and reviews.  
- 🐘 **PostgreSQL** – A powerful relational database for storing structured data such as users, property listings, and bookings.  
- 🔎 **GraphQL** – Enables flexible and efficient querying of data, allowing clients to request exactly what they need.  
- ⏳ **Celery** – Handles background tasks such as sending notifications and processing asynchronous jobs (e.g., payments).  
- ⚡ **Redis** – Used for caching and session management to improve performance and reduce database load.  
- 🐳 **Docker** – Provides containerization for consistent development and deployment environments.  
- 🤖 **GitHub Actions (CI/CD)** – Automates testing and deployment pipelines to ensure smooth integration and delivery.  

## 🗄️ Database Design  

The backend uses a relational database (PostgreSQL) to manage key entities and their relationships:  

### 👤 Users

**Key Fields:**

- `id` – Unique user identifier  
- `name` – Full name of the user  
- `email` – Unique email for login and communication  
- `password` – Hashed password for authentication  
- `role` – User role (e.g., guest, host)  

**Relationships:**

- A user can **own multiple properties** 🏡  
- A user can **make multiple bookings** 📅  
- A user can **write multiple reviews** ⭐  

---

### 🏡 Properties

**Key Fields:**

- `id` – Unique property identifier  
- `title` – Property title or name  
- `description` – Details about the property  
- `price_per_night` – Cost per night stay  
- `owner_id` – References the user who owns the property  

**Relationships:**

- Each property **belongs to one user** 👤  
- Each property can have **multiple bookings** 📅  
- Each property can have **multiple reviews** ⭐  

---

### 📅 Bookings

**Key Fields:**  

- `id` – Unique booking identifier  
- `property_id` – The property being booked  
- `user_id` – The user making the booking  
- `check_in` – Check-in date  
- `check_out` – Check-out date  

**Relationships:**  

- A booking **belongs to one property** 🏡  
- A booking **belongs to one user** 👤  

---

### ⭐ Reviews  

**Key Fields:**  

- `id` – Unique review identifier  
- `property_id` – The property being reviewed  
- `user_id` – The user who wrote the review  
- `rating` – Numerical rating (e.g., 1–5)  
- `comment` – Review text  

**Relationships:**  

- A review **belongs to one property** 🏡  
- A review **belongs to one user** 👤  

---

### 💳 Payments

**Key Fields:**  

- `id` – Unique payment identifier  
- `booking_id` – Associated booking  
- `amount` – Total amount paid  
- `payment_method` – e.g., Credit Card, PayPal  
- `status` – Payment status (completed, pending, failed)  

**Relationships:**

- A payment **belongs to one booking** 📅  
- Each booking can have **one or multiple payments** 💳  
