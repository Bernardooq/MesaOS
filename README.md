# 🍽️ DineSync ERP (Restaurant Enterprise Resource Planning)

An incredibly comprehensive, cloud-native Enterprise Resource Planning (ERP) system tailored specifically for the restaurant and hospitality industry. This platform manages the entire lifecycle of restaurant operations, from real-time table management and reservations to inventory, billing, and staff administration.

## 🚀 Overview

DineSync ERP is designed to handle the rigorous demands of modern dining establishments. Deployed entirely on AWS, it utilizes a dual-backend architecture to optimize performance: **NestJS** handles robust business logic, user management, and core relational processes, while **FastAPI** drives high-performance, asynchronous tasks and real-time data processing. 

## ✨ Core Features

* **📅 Advanced Reservation System:** Real-time booking engine, waitlist management, and automated customer notifications.
* **🗺️ Dynamic Table Management:** Interactive, customizable floor plans with real-time table status (occupied, reserved, cleaning, available).
* **📦 Intelligent Inventory & Supply Chain:** Automated stock tracking, recipe costing, and supplier purchase order generation.
* **💳 Comprehensive POS (Point of Sale):** Seamless order taking, split billing, payment gateway integration, and digital receipt generation.
* **👥 HR & Staff Management:** Role-based access control (RBAC), shift scheduling, performance tracking, and payroll integrations.
* **📊 Analytics & Reporting:** Real-time dashboards detailing daily revenue, peak hours, best-selling items, and table turnover rates.

## 🛠️ Technology Stack

* **Core Backend (Business Logic):** [NestJS](https://nestjs.com/)
* **High-Performance Service (Real-time/Data):** [FastAPI](https://fastapi.tiangolo.com/) (Python)
* **Database:** [PostgreSQL](https://www.postgresql.org/) (Relational Data & Transactions)
* **Cloud Infrastructure:** Amazon Web Services (AWS)
    * *Database Hosting:* Amazon RDS
    * *Compute/Deployment:* AWS EC2 / ECS
    * *Storage:* Amazon S3 (for assets, menus, user uploads)

## 🏗️ Architecture

This project implements a service-oriented architecture. The NestJS application serves as the primary gateway and business logic handler, providing strict typing and scalable modularity. The FastAPI microservice is coupled to handle concurrent requests efficiently, particularly for real-time table state updates and complex analytical queries. Data integrity is maintained across a highly available PostgreSQL cluster on AWS.

## 💻 Local Development Setup

### Prerequisites
* Node.js (v18+)
* Python (3.10+)
* Docker & Docker Compose

### Installation Steps

1. **Clone the repository**
    ```bash
    git clone [https://github.com/yourusername/dinesync-erp.git](https://github.com/yourusername/dinesync-erp.git)
    cd dinesync-erp
    ```

2. **Environment Variables**
    Copy the `.env.example` files in both the `nestjs-core` and `fastapi-service` directories and update the database and AWS credentials.
    ```bash
    cp nestjs-core/.env.example nestjs-core/.env
    cp fastapi-service/.env.example fastapi-service/.env
    ```

3. **Spin up the database and services via Docker**
    ```bash
    docker-compose up -d
    ```

4. **Run Migrations**
    ```bash
    # Run Prisma/TypeORM migrations for NestJS
    cd nestjs-core && npm run migration:run
    
    # Run Alembic migrations for FastAPI
    cd ../fastapi-service && alembic upgrade head
    ```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
