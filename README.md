# Item Manager - MERN Stack Lab Test

A full-stack web application for managing items with CRUD operations.

## Features
- View all items in a grid layout
- Add new items with form validation
- Edit existing items
- Delete items with confirmation
- Responsive design
- MongoDB database integration

## Tech Stack
- **Frontend**: React, React Router, Axios, Vite
- **Backend**: Node.js, Express, MongoDB, Mongoose
- **Database**: MongoDB

## Project Structure
```
WMT_LabTest_Project/
├── backend/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── server.js
│   ├── package.json
│   └── .env
└── frontend/
    ├── src/
    │   ├── components/
    │   ├── pages/
    │   ├── api/
    │   ├── App.jsx
    │   └── main.jsx
    ├── index.html
    ├── package.json
    └── .env
```

## Setup Instructions

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local installation or Atlas account)

### Backend Setup
1. Navigate to the backend folder
2. Install dependencies: `npm install`
3. Set up environment variables in `.env`
4. Start the server: `npm run dev`

### Frontend Setup
1. Navigate to the frontend folder
2. Install dependencies: `npm install`
3. Set up environment variables in `.env`
4. Start the development server: `npm run dev`

### MongoDB Setup
- **Local MongoDB**: Install from https://www.mongodb.com/try/download/community
- **MongoDB Atlas**: Create a free cluster at https://www.mongodb.com/atlas

Update the `MONGO_URI` in `backend/.env` accordingly.

## Usage
1. Start the backend server
2. Start the frontend development server
3. Open http://localhost:5173 in your browser
4. Use the interface to manage items

## API Documentation
The backend provides RESTful API endpoints for item management.

Base URL: `http://localhost:5000/api`

- `GET /items` - Retrieve all items
- `GET /items/:id` - Retrieve a specific item
- `POST /items` - Create a new item
- `PUT /items/:id` - Update an existing item
- `DELETE /items/:id` - Delete an item