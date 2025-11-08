# 💰 SplitEase: Simplify Group Expenses

SplitEase is a web application designed to simplify the process of managing and settling shared expenses within groups. It allows users to create groups, add members, record expenses, and automatically calculate the optimal way to settle debts, minimizing the number of transactions required. Say goodbye to complicated spreadsheets and awkward IOUs!

## 🚀 Key Features

- **Group Management:** Create and manage groups of friends, family, or colleagues.
- **Member Management:** Easily add and remove members from groups.
- **Expense Tracking:** Record shared expenses with details like amount, category, and description.
- **Transaction Recording:** Automatically record transactions between users within a group.
- **Intelligent Settlement:** Utilizes a maximum flow algorithm to calculate the optimal payment plan, minimizing the number of transactions needed to settle debts.
- **User Authentication:** Secure user registration and login with password hashing and JWT-based authentication.
- **Email Invitations:** Invite new users to join the platform via email.
- **Username Availability Check:** Ensures unique usernames during registration.

## 🛠️ Tech Stack

*   **Frontend:** (Description not provided, assuming common web technologies)
    *   React
    *   JavaScript
    *   HTML
    *   CSS
*   **Backend:**
    *   Node.js
    *   Express.js
*   **Database:**
    *   MongoDB
    *   Mongoose (ODM)
*   **Authentication:**
    *   JSON Web Tokens (JWT)
    *   bcrypt (Password Hashing)
*   **Other:**
    *   cors (Cross-Origin Resource Sharing)
    *   dotenv (Environment Variable Management)

## 📦 Getting Started / Setup Instructions

### Prerequisites

- Node.js and npm installed on your machine.
- MongoDB installed and running or a MongoDB Atlas account.

### Installation

1.  Clone the repository:

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  Navigate to the backend directory:

    ```bash
    cd backend
    ```

3.  Install backend dependencies:

    ```bash
    npm install
    ```

4.  Create a `.env` file in the `backend` directory and configure the following environment variables:

    ```
    PORT=3000  # Or any other available port
    MONGODB_URI=<your_mongodb_connection_string>
    JWT_SECRET=<your_secret_key> # Use a strong, randomly generated secret key
    SALT_ROUNDS=10 # Or any other number of salt rounds for bcrypt
    EMAIL_USER=<your_email_address>
    EMAIL_PASS=<your_email_password>
    ```

    **Important:** Replace `<your_mongodb_connection_string>`, `<your_secret_key>`, `<your_email_address>`, and `<your_email_password>` with your actual values.

5.  Navigate to the frontend directory (if applicable):

    ```bash
    cd ../frontend 
    ```

6.  Install frontend dependencies:

    ```bash
    npm install # or yarn install
    ```

### Running Locally

1.  Start the backend server:

    ```bash
    cd backend
    node app.js
    ```

    This will start the backend server on the port specified in your `.env` file (default is 3000).

2.  Start the frontend development server:

    ```bash
    cd ../frontend 
    npm run dev
    ```

    This will typically start the frontend development server on `http://localhost:5173` or a similar address.

## 📂 Project Structure

```
splitease/
├── backend/
│   ├── app.js               # Main entry point for the backend application
│   ├── middleware/
│   │   └── authMiddleware.js  # Middleware for JWT authentication
│   ├── controllers/
│   │   ├── authControllers.js     # User authentication controllers (register, login)
│   │   ├── expenseControllers.js  # Expense-related controllers (create, get)
│   │   ├── groupControllers.js    # Group-related controllers (create, get, add members)
│   │   ├── transactionControllers.js # Transaction controllers (create, get, delete)
│   │   ├── userControllers.js       # User controllers (check if user exists)
│   │   ├── resultsController.js     # Controller for calculating settlement results
│   │   └── inviteControllers.js    # Controller for sending email invitations
│   ├── helpers/
│   │   ├── bfs.js                  # Breadth-First Search algorithm
│   │   ├── calculateNetBalances.js # Calculates net balances between users
│   │   ├── createFlowGraphMatrix.js # Creates the flow graph matrix for settlement
│   │   └── maxFlowAlgo.js          # Maximum flow algorithm for settlement optimization
│   ├── models/
│   │   ├── expenseModel.js      # Mongoose model for expenses
│   │   ├── groupModel.js        # Mongoose model for groups
│   │   ├── transactionModel.js  # Mongoose model for transactions
│   │   └── userModel.js         # Mongoose model for users
│   ├── routes/
│   │   ├── authRoutes.js        # Authentication routes
│   │   ├── expenseRoutes.js     # Expense routes
│   │   ├── groupRoutes.js       # Group routes
│   │   ├── transactionRoutes.js # Transaction routes
│   │   └── resultsRoutes.js     # Results routes
│   ├── utils/
│   │   └── mailer.js            # Utility for sending emails
│   ├── .env                   # Environment variables (API keys, database URI, etc.)
│   └── package.json           # Backend dependencies and scripts
├── frontend/
│   ├── ...                    # Frontend source code (React components, etc.)
│   ├── package.json           # Frontend dependencies and scripts
├── .gitignore               # Specifies intentionally untracked files that Git should ignore
└── README.md                # This file!
```


