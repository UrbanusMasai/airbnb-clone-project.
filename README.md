# airbnb-clone-project.
A backend-focused Airbnb Clone project exploring database design, API development, security, and deployment with Django, PostgreSQL, GraphQL, and Docker.
# Airbnb Clone Project

This project is a backend-focused simulation of an Airbnb-like booking platform.  
It explores **real-world software development practices**, including database design, API development, security, and CI/CD deployment.

---

##  Project Goals
- Master collaborative team workflows using GitHub.  
- Deepen understanding of backend architecture and relational database design.  
- Implement secure and scalable API systems.  
- Learn CI/CD automation for smooth deployments.  
- Integrate modern tools like **Django, PostgreSQL, GraphQL, and Docker**.  

---

##  Technology Stack
- **Django** → Backend framework for APIs, authentication, and business logic.  
- **PostgreSQL** → Relational database for structured data.  
- **GraphQL** → API query language for flexible data retrieval.  
- **Docker** → Containerization for deployment and environment consistency.  
- **GitHub Actions** → CI/CD pipeline automation.  
---

##  Team Roles

This project simulates a real-world software development team.  
Each role contributes to the success of the Airbnb Clone project:

- **Backend Developer** → Builds and maintains the core application logic, REST/GraphQL APIs, authentication, and integrations with the database.  
- **Database Administrator (DBA)** → Designs, manages, and optimizes the database structure, ensuring data consistency, security, and performance.  
- **DevOps Engineer** → Manages CI/CD pipelines, Docker containers, and deployment environments to guarantee smooth and scalable releases.  
- **Project Manager** → Coordinates tasks, manages timelines, and ensures that the team follows agile practices and project objectives.  
- **QA Engineer (Tester)** → Validates features, writes test cases, and ensures the system is secure, bug-free, and performs well before release.  
- **Security Engineer** → Focuses on protecting user data, securing APIs, and implementing best practices to prevent vulnerabilities.  
---

##  Technology Stack  

This project leverages a modern backend-focused technology stack to build a scalable, secure, and efficient Airbnb-like booking platform. Each technology has a clear purpose in achieving project goals:  

- **Django** → A high-level Python web framework used to build backend logic, manage authentication, and expose RESTful/GraphQL APIs.  
- **PostgreSQL** → A powerful relational database for storing and managing structured data such as users, properties, bookings, and payments.  
- **GraphQL** → A flexible query language and runtime for APIs, enabling clients to request only the data they need, improving performance.  
- **Docker** → Provides containerization to ensure the app runs consistently across different environments (development, staging, production).  
- **GitHub Actions (CI/CD)** → Automates testing, deployment, and integration pipelines to ensure efficient and reliable releases.  
- **Nginx** → Used as a reverse proxy and load balancer to handle client requests efficiently and improve scalability.  

---
---

###🗄 Database Design  

The database is designed to support core Airbnb-like functionalities, ensuring scalability, data integrity, and clear relationships between entities.  

### **Key Entities & Fields**  

1. **Users**  
   - `id` (Primary Key)  
   - `name`  
   - `email` (unique)  
   - `password_hash`  
   - `role` (guest, host, admin)  

2. **Properties**  
   - `id` (Primary Key)  
   - `user_id` (Foreign Key → Users)  
   - `title`  
   - `description`  
   - `location`  
   - `price_per_night`  

3. **Bookings**  
   - `id` (Primary Key)  
   - `user_id` (Foreign Key → Users)  
   - `property_id` (Foreign Key → Properties)  
   - `start_date`  
   - `end_date`  
   - `status` (pending, confirmed, cancelled)  

4. **Reviews**  
   - `id` (Primary Key)  
   - `user_id` (Foreign Key → Users)  
   - `property_id` (Foreign Key → Properties)  
   - `rating` (1–5)  
   - `comment`  

5. **Payments**  
   - `id` (Primary Key)  
   - `booking_id` (Foreign Key → Bookings)  
   - `amount`  
   - `payment_date`  
   - `status` (completed, pending, failed)  

### **Entity Relationships**  
- A **User** can list multiple **Properties**.  
- A **User** can make multiple **Bookings**.  
- A **Booking** is linked to a single **Property**.  
- A **User** can leave multiple **Reviews**, but only one review per booking/property.  
- A **Payment** is tied to a single **Booking**.  

---

