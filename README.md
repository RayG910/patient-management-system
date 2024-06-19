# Patient Management System

A web application to manage patient records and appointments, built using Node.js, Express, MySQL, and React.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Features

- User authentication and authorization
- Patient management (CRUD operations)
- Appointment scheduling
- Responsive user interface
- RESTful API

## Installation

### Prerequisites

- [Node.js](https://nodejs.org/) and npm
- [XAMPP](https://www.apachefriends.org/index.html) (or any other method to run MySQL and Apache)
- [Git](https://git-scm.com/)

### Steps

1. **Clone the repository:**
    ```bash
    git clone https://github.com/rayg910/patient-management-system.git
    cd patient-management-system
    ```

2. **Set up the backend:**
    - Navigate to the `backend` directory:
      ```bash
      cd backend
      ```
    - Install the dependencies:
      ```bash
      npm install
      ```
    - Create a `.env` file with the following content:
      ```
      DB_HOST=localhost
      DB_USER=root
      DB_PASSWORD=
      DB_NAME=patient_management
      JWT_SECRET=your_jwt_secret
      ```
    - Start XAMPP and ensure Apache and MySQL are running.
    - Create a database named `patient_management` using phpMyAdmin or any other method.
    - Run the backend server:
      ```bash
      nodemon app.js
      ```

3. **Set up the frontend:**
    - Navigate to the `frontend` directory:
      ```bash
      cd ../frontend
      ```
    - Install the dependencies:
      ```bash
      npm install
      ```
    - Start the React development server:
      ```bash
      npm start
      ```

## Usage

1. **Register a new user:**
    - Open your browser and navigate to `http://localhost:3000/register`.
    - Fill out the registration form and submit.

2. **Log in:**
    - Navigate to `http://localhost:3000/`.
    - Enter your credentials and submit.

3. **Manage patients and appointments:**
    - After logging in, you will be redirected to the dashboard where you can manage patients and appointments.

## API Endpoints

### User Endpoints

- **POST /api/users/register**
  - Registers a new user.
  - Request body: `{ "name": "string", "email": "string", "password": "string", "role": "string" }`
  
- **POST /api/users/login**
  - Authenticates a user and returns a JWT.
  - Request body: `{ "email": "string", "password": "string" }`

### Patient Endpoints

- **GET /api/patients**
  - Returns a list of all patients.
  
- **POST /api/patients**
  - Adds a new patient.
  - Request body: `{ "name": "string", "age": "number", "address": "string", "phone": "string" }`

- **PUT /api/patients/:id**
  - Updates a patient's information.
  - Request body: `{ "name": "string", "age": "number", "address": "string", "phone": "string" }`

- **DELETE /api/patients/:id**
  - Deletes a patient.

### Appointment Endpoints

- **GET /api/appointments**
  - Returns a list of all appointments.
  
- **POST /api/appointments**
  - Schedules a new appointment.
  - Request body: `{ "patientId": "number", "date": "string", "time": "string", "reason": "string" }`

- **PUT /api/appointments/:id**
  - Updates an appointment.
  - Request body: `{ "date": "string", "time": "string", "reason": "string" }`

- **DELETE /api/appointments/:id**
  - Cancels an appointment.

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Create a new Pull Request.

## License

This project is licensed under the MIT License.
