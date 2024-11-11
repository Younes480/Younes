# Online Library Management System

## Description

An online library management system built using **NestJS** for the backend and  **React** for the frontend. It allows users to manage books, authors, user accounts, and book reviews.

This project is divided into two main parts:

- **Backend** (m1-api): Manages data (books, authors, user accounts) and handles server-side logic.
- **Frontend** (m1-site): A web interface to interact with the data, providing a friendly user experience.

## Tech Stack

- **Backend**: NestJS
- **Frontend**: React
- **Database**: MySQL
- **Authentication**: Session-based (instead of JWT)
- **Libraries**: Tailwind CSS for styling, Class-validator for backend validation, and TypeORM for database interaction.

## Installation

### Prerequisites

- **Node.js** (version 14 or above)
- **npm** or **yarn**
- **MySQL**

### Installation Steps

1. **Clone the Repository**

   ```bash
   git clone https://github.com/dev-sheikh-ali/online_library.git
   cd online_library
   ```

2. **Backend Setup (NestJS)**

   ```bash
   cd m1-api
   npm install
   ```

   **Environment Variables**

   Create a `.env` file in the `m1-api` directory with the following content:

   ```env
   PORT=3001
   DB_HOST=localhost
   DB_PORT=3306
   DB_USERNAME= your_db_user
   DB_PASSWORD= your_db_user_pass
   DB_DATABASE=online_library
   SESSION_SECRET= generate_with_node
   ```

   **Running the Backend Server**

   ```bash
   npm run start:dev
   ```

   The backend server will run by default on **[http://localhost:3001](http://localhost:3001)**.

3. **Frontend Setup (Next.js)**

   ```bash
   cd ../m1-site
   npm install
   ```

   **Environment Variables**

   Create a `.env.local` file in the `m1-site` directory with the following content:

   ```env
   NEXT_PUBLIC_API_URL=http://localhost:3001
   ```

   **Running the Frontend Server**

   ```bash
   npm run dev
   ```

   The frontend server will run by default on **[http://localhost:3000](http://localhost:3000)**.

## Project Structure

### Backend Project Structure

The backend follows a modular approach, with each module focused on a specific domain such as books, authors, or user management.

```bash
m1-api
├── nest-cli.json
├── package.json
├── package-lock.json
├── README.md
├── src
│   ├── app.module.ts
│   ├── main.ts
│   └── modules
│       ├── author_management
│       ├── book_management
│       ├── review_management
│       └── user_management
│           ├── entities
│           │   └── user.entity.ts
│           ├── strategies
│           │   └── local.strategy.ts
│           ├── user_management.controller.ts
│           ├── user_management.module.ts
│           └── user_management.service.ts
└── tsconfig.json
```

### Frontend Project Structure

The frontend is structured to create reusable components, layouts, and pages to provide a modular and scalable approach.

```bash
m1-site/
├── next.config.js
├── package.json
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robots.txt
├── src
│   ├── api
│   │   └── userApi.ts
│   ├── components
│   │   ├── Modal.tsx
│   │   └── Navbar.tsx
│   ├── modules
│   │   └── user_management
│   │       └── components
│   │           ├── LoginForm.tsx
│   │           ├── ProfileForm.tsx
│   │           └── SignupForm.tsx
│   ├── pages
│   │   └── user
│   ├── styles
│   │   └── globals.css
│   └── app
│       ├── App.css
│       ├── layout.tsx
│       └── page.tsx
└── tailwind.config.js
```

## Backend Modules Overview

### Author Management Module

Handles CRUD operations for authors.

**Files**:

- **`author.controller.ts`**: Manages API endpoints for authors.
- **`author.service.ts`**: Contains the logic for author-related operations.
- **`dto/`**: Defines the data that can be sent or received.
- **`entities/`**: Defines the author model stored in the database.

### Book Management Module

Manages CRUD operations for books.

**Files**:

- **`book.controller.ts`**: Handles endpoints for book actions.
- **`book.service.ts`**: Business logic for managing books.
- **`dto/`**: Defines book data for APIs.
- **`entities/`**: Defines the book model.

### User Management Module

Manages user registrations, profile updates, etc.

**Files**:

- **`user_management.controller.ts`**: Handles user endpoints.
- **`user_management.service.ts`**: Contains user authentication and management logic.
- **`dto/`**: User registration, login, and update details.
- **`entities/`**: User model definitions.

### Review Management Module

Allows users to add reviews to books.

**Files**:

- **`review.controller.ts`**: Handles review-related endpoints.
- **`review.service.ts`**: Contains business logic for managing book reviews.
- **`dto/`**: Defines the data that can be sent or received for reviews.
- **`entities/`**: Defines the review model for the database.

## Usage

1. **Open the browser** and navigate to **[http://localhost:3000](http://localhost:3000)** to access the frontend.
2. Use the frontend UI to **create an account**, **login**, **add authors**, **add books**, and **write reviews**.

## Features Implemented So Far

- User registration, login, and profile management.
- 

## Upcoming Features


- Improved authentication and user role management.
- Pagination for books and authors listing.
- Author Management: CRUD operations for authors.
- Book Management: CRUD operations for books.
- Review Management: Allow users to add reviews to books.
- Advanced search functionality for books and authors.

Feel free to contribute to the project by creating pull requests or submitting issues on GitHub.
