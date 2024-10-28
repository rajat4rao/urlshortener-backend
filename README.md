# URL Shortener Application

This project implements a URL shortening web application with both frontend and backend components, featuring user authentication and usage analytics.

## Features

### Authentication System

A comprehensive authentication system handles user login, registration, and password recovery:

* **User Registration:**
    * Collects username (unique email address), first name, last name, and password (encrypted).
    * Implements a two-step activation workflow:
        1. Creates an inactive account upon signup.
        2. Sends an activation email with a unique link.
        3. Activates the account upon clicking the link.
    * Only activated users can log in.
    * Displays clear messages for unregistered users attempting to log in.
* **Login:** Securely authenticates registered and activated users.
* **Forgot Password:**
    1. User clicks "Forgot Password" and is redirected.
    2. System validates the user's email address.
    3. System sends an email with a randomly generated token embedded in a URL for password reset.  This token and URL are temporarily stored in the database.
    4. User clicks the URL and resets their password.
    5. The system deactivates the token and updates the user's password in the database.
    6. System displays a success message.

### User Interface

* **Dashboard:** Displays charts visualizing the total number of URLs created per day and within a month.
* **URL Creation Modal/Page:** Provides an interface for users to submit long URLs and generate shortened versions.
* **URL List Page:** Displays a table listing all created shortened URLs, along with associated analytics.


## Processing and Output

* **Short URL Generation:**  The system takes a long URL as input and generates a unique, shortened URL.
* **Redirection:** Accessing a shortened URL redirects the user to the original long URL.
* **Click Tracking:** The system tracks the number of clicks for each shortened URL.
* **User Feedback:**  The system uses alerts to provide feedback to the user (e.g., successful URL creation, errors, etc.).


## Technical Specifications

- **Frontend:** React, Bootstrap (via CDN), React Toastify
- **Backend:** Node.js, Express
- **Database:** MongoDB
- **Charting:** Chart.js
- **Authentication**: JSON Web Tokens (JWT)
- **Email Service**: Nodemailer



## Deployed URL:

- **Frontend**: [https://urlshortener-frontend2.netlify.app/](https://urlshortener-frontend2.netlify.app/)
- **Backend**: `https://urlshortener-backend-sr2i.onrender.com`

---

## Usage

1. **Register:** Create a new account or log in with an existing account.
2. **Shorten URLs:** Use the form to shorten a long URL.
3. **View URLs:** Access the dashboard to see your shortened URLs and their analytics.

---

## Routes

- **POST /api/urls/shorten** - Shorten a URL
- **GET /api/urls/** - Get a list of URLs
- **GET /api/urls/:id** - Get details of a specific URL
- **GET /api/urls/dash/count** - Get dashboard data
- **POST /api/auth/register** - Register a new user
- **POST /api/auth/login** - Log in an existing user

---
