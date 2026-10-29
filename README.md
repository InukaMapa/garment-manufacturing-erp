
# Garment Manufacturing ERP System

A Web-Based Enterprise Resource Planning System for Garment Manufacturing

![Project](https://img.shields.io/badge/Project-Academic%20ERP-blue)
![Frontend](https://img.shields.io/badge/Frontend-Vue.js-42b883)
![Backend](https://img.shields.io/badge/Backend-Laravel-ff2d20)
![Database](https://img.shields.io/badge/Database-MySQL-4479A1)
![API](https://img.shields.io/badge/API-REST-orange)

## Overview

The Garment Manufacturing ERP System is a web-based application
designed to streamline and integrate the core operational processes
of a garment manufacturing factory.

The system manages the complete internal business workflow, from
customer order processing and raw-material procurement to inventory
management, production, quality assurance, dispatch, and invoicing.

Built using Vue.js, Laravel REST APIs, and MySQL, the system aims to
improve operational visibility, maintain data consistency, reduce
manual record-keeping, and support efficient coordination between
factory departments.

This project is developed as an academic Software Engineering project
with a modular architecture and clearly defined functional
responsibilities.

## Project Objectives

- Centralize garment manufacturing operations in one system.
- Manage customer orders, garment styles, and delivery dates.
- Organize supplier records and purchase orders.
- Track raw materials, receipts, issues, and stock balances.
- Calculate material requirements using Bills of Materials (BOM).
- Monitor production quantities and material wastage.
- Record garment inspections and quality outcomes.
- Control dispatch quantities based on approved garments.
- Generate invoices for dispatched quantities.
- Provide filterable reports with CSV export.
- Maintain data integrity through server-side validation and
  role-based access control.

## Key Features

### 1. Customer Management
- Create, update, and search customer records.
- Maintain contact information.
- Select registered customers when creating orders.
- Generate a filterable Customer List report.

### 2. Order Management
- Maintain garment styles, sizes, and colours.
- Create orders with quantities, unit prices, and delivery dates.
- Track order status.
- Generate an Order Status report.

### 3. Supplier Management
- Create, update, and search supplier records.
- Maintain supplier contact information.
- Select suppliers when preparing purchase orders.
- Generate a Supplier List report.

### 4. Purchase Order Management
- Create purchase orders for raw materials.
- Record suppliers, ordered quantities, and unit costs.
- Track received and outstanding quantities.
- Generate a Purchase Order Status report.

### 5. Materials and Bill of Materials (BOM)
- Maintain a raw-material catalogue.
- Define material requirements for each garment style.
- Calculate material requirements for customer orders.
- Generate a Material Requirement report.

### 6. Goods Received Note (GRN) Management
- Record material receipts against existing purchase orders.
- Capture receipt dates and quantities.
- Prevent receipts exceeding outstanding purchase quantities.
- Generate a GRN report.

### 7. Raw-Material Inventory Management
- Monitor material stock balances.
- Record material receipts and production issues.
- Issue available materials against production orders.
- Prevent negative stock balances.
- Generate a Stock Balance report.

### 8. Production Management
- Record cutting and completed production quantities.
- Track materials used and production wastage.
- Associate production records with customer orders.
- Generate a Daily Production report.

### 9. Quality Assurance (QA)
- Record inspections of produced garments.
- Track approved, defective, and rework quantities.
- Prevent inspection quantities from exceeding eligible
  completed production.
- Generate a QA Inspection report.

### 10. Dispatch Management
- Dispatch garments approved by quality assurance.
- Record delivery note numbers and dispatch dates.
- Prevent dispatch beyond eligible approved quantities.
- Generate a Dispatch Summary report.

### 11. Invoicing Management
- Create invoices for dispatched garment quantities.
- Calculate invoice amounts using order-linked unit prices.
- Track basic paid and unpaid statuses.
- Generate a Sales Invoice report.

## Business Workflow

The system follows an integrated garment manufacturing workflow:

Customer Registration
        |
        v
Customer Order
        |
        v
Bill of Materials (BOM)
        |
        v
Purchase Order
        |
        v
Goods Receipt (GRN)
        |
        v
Raw-Material Inventory
        |
        v
Material Issue to Production
        |
        v
Production Recording
        |
        v
Quality Assurance
        |
        v
Dispatch Management
        |
        v
Invoice Generation

Each transaction is linked to its relevant source record to support
traceability and consistency across the manufacturing process.

## Technology Stack

### Frontend
- Vue.js
- JavaScript
- HTML5
- CSS3

### Backend
- Laravel
- PHP
- RESTful API architecture

### Database
- MySQL
- Relational data modelling
- Database migrations and relationships

### Development Tools
- Git
- GitHub
- Composer
- Node.js and npm
- Postman or an equivalent API testing tool

## System Architecture

The application follows a client-server architecture.

1. The Vue.js frontend provides the user interface, forms,
   navigation, tables, and report views.
2. The Laravel backend exposes REST API endpoints, validates
   incoming requests, enforces business rules, and processes
   transactions.
3. The MySQL database stores users, customers, suppliers, orders,
   materials, stock movements, production records, QA inspections,
   dispatches, and invoices.

The frontend communicates with the backend through HTTP requests.
The backend manages access control and database operations.

## User Roles

The system is intended for internal factory staff.

- Administrator
- Garment Clerk
- Purchasing Officer
- Storekeeper
- Production Officer
- QA Officer

Role-based access determines which functions users can access.
Customers are maintained as business records and do not log in
to the system.

## Reports and Exports

Each functional module provides a report with relevant filters,
an on-screen data table, and CSV export.

| Module | Report |
|---|---|
| Customer Management | Customer List |
| Order Management | Order Status |
| Supplier Management | Supplier List |
| Purchase Orders | PO Status |
| Materials and BOM | Material Requirement |
| Goods Receipt | GRN Report |
| Inventory | Stock Balance |
| Production | Daily Production |
| Quality Assurance | QA Inspection |
| Dispatch | Dispatch Summary |
| Invoicing | Sales Invoice |

## Business Rules and Data Integrity

The system enforces essential manufacturing controls:

- Goods received cannot exceed outstanding purchase-order quantities.
- Material issues cannot exceed available stock.
- Inventory balances are calculated from receipts and issues.
- Stock balances must not become negative.
- Dispatch quantities cannot exceed eligible QA-approved quantities
  or the remaining order balance.
- Production, inspection, dispatch, and invoicing quantities must
  remain reconcilable.
- Required fields and business validations are enforced by Laravel.
- Transactions must maintain relationships with their source records.
- Related stock and financial changes should be handled safely
  using database transactions.
- User access must follow authentication and role restrictions.

## Security Considerations

- Authenticated access for internal users.
- Role-based authorization for protected operations.
- Server-side input validation.
- Secure password storage.
- Controlled access to API endpoints.
- Referential integrity between related records.
- Validation of quantities before committing transactions.

## Project Structure

The following is a suggested repository organization. Adapt it to
the actual structure agreed upon by the development team.

    garment-manufacturing-erp/
    |
    |-- frontend/
    |   |-- src/
    |   |   |-- components/
    |   |   |-- views/
    |   |   |-- services/
    |   |   |-- router/
    |   |   |-- assets/
    |   |   `-- App.vue
    |   `-- package.json
    |
    |-- backend/
    |   |-- app/
    |   |-- routes/
    |   |-- database/
    |   |   |-- migrations/
    |   |   `-- seeders/
    |   |-- tests/
    |   `-- composer.json
    |
    |-- docs/
    |   |-- requirements/
    |   |-- diagrams/
    |   |-- api-documentation/
    |   `-- test-cases/
    |
    |-- .gitignore
    `-- README.md

## Getting Started

### Prerequisites

Install the following tools before setting up the application:

- Git
- Node.js and npm
- PHP compatible with the selected Laravel version
- Composer
- MySQL
- A compatible web browser

### 1. Clone the Repository

    git clone <YOUR_REPOSITORY_URL>
    cd garment-manufacturing-erp

### 2. Set Up the Backend

    cd backend
    composer install

Create the environment configuration file:

    cp .env.example .env

Generate the Laravel application key:

    php artisan key:generate

Configure the database connection in the backend `.env` file.

Example:

    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=garment_erp
    DB_USERNAME=your_database_username
    DB_PASSWORD=your_database_password

Create the `garment_erp` database in MySQL, then run:

    php artisan migrate

Start the Laravel development server:

    php artisan serve

### 3. Set Up the Frontend

Open a new terminal:

    cd frontend
    npm install

Configure the frontend API base URL to point to the running
Laravel backend, using the environment variable convention
supported by the project.

Start the frontend development server:

    npm run dev

Open the local URL displayed in the terminal.

Note: These instructions assume the suggested `frontend/` and
`backend/` folder structure. Update commands and configuration
according to the actual repository and application setup.

## Testing

Testing should cover both individual modules and the complete
manufacturing workflow.

Recommended test scenarios include:

- Valid and invalid customer and supplier records.
- Order creation and status updates.
- Purchase-order and GRN quantity validation.
- Material requirement calculations.
- Stock issue validation and negative-stock prevention.
- Production quantity and wastage validation.
- QA inspection quantity validation.
- Dispatch quantity validation.
- Invoice amount and status verification.
- Report filtering and CSV export.
- Authentication and role-based authorization.

Each assigned module should include at least five test cases,
followed by end-to-end integration testing.

## Development Methodology

The project follows an eight-week development schedule.

- Week 1: UI wireframes and report layouts.
- Weeks 2–3: Frontend development using mock data.
- Week 4: Workflow design, ERD, API contracts, and database design.
- Weeks 5–7: Backend development, validations, report queries,
  and frontend-backend integration.
- Week 8: Integration testing, defect fixes, report exports,
  and final demonstration.

The team uses a shared Git repository, consistent naming conventions,
agreed API response formats, and coordinated database migrations.

## Project Scope

This project focuses on core garment factory operations and is
intended as an academic ERP prototype.

The following are outside the defined scope:

- Customer-facing login portal.
- Online payment gateway.
- Advanced accounting.
- Credit top-ups.
- Multiple BOM version management.
- Complex approval workflows.
- Automated notifications.
- External system integrations.

Additional features should be agreed upon by the team before
implementation.

## Contributors

This project is developed collaboratively by a team of 11 students.

Contributors are responsible for their assigned modules, including
frontend screens, backend APIs, database changes, validations,
reports, and module-level testing.

Add team member names and GitHub profiles here.

## Future Improvements

Potential enhancements, subject to team approval, include:

- Advanced production analytics and dashboards.
- More detailed inventory forecasting.
- Enhanced reporting and data visualization.
- Automated notifications.
- Integration with external business systems.

These are possible future enhancements and are not part of the
currently defined minimum scope.

## License

No license has been specified yet. Add an appropriate LICENSE file
if the project is intended to be distributed or reused publicly.

---

Developed as a Software Engineering academic project.

Garment Manufacturing ERP System
