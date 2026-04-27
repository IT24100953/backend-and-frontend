# MERN Item Manager - Deployment Guide

## Backend Deployment (Railway)

### Prerequisites:
- Railway Account (create at https://railway.app)
- GitHub Repository (already pushed)

### Steps:
1. Go to https://railway.app/dashboard
2. Click "New Project"
3. Select "Deploy from GitHub"
4. Connect your GitHub account and select the repository
5. Railway will auto-detect the Node.js backend
6. Configure environment variables:
   - `PORT`: 5000
   - `MONGO_URI`: Your MongoDB connection string
7. Deploy the project
8. Once deployed, you'll get a live URL (e.g., https://your-app.railway.app)
9. Note the backend URL for the next step

## Frontend Deployment (Netlify)

### Prerequisites:
- Netlify Account (create at https://netlify.com)
- Backend URL from Railway deployment

### Steps:
1. Update `frontend/.env` with the deployed backend URL:
   ```
   VITE_API_URL=https://your-backend-url.railway.app/api
   ```

2. Build the frontend:
   ```bash
   cd frontend
   npm run build
   ```

3. Go to https://app.netlify.com
4. Click "Add new site" → "Import an existing project"
5. Select your GitHub repository
6. Set build settings:
   - Build command: `cd frontend && npm run build`
   - Publish directory: `frontend/dist`
7. Deploy

### Verification:
- Backend API endpoint: `https://your-backend-url.railway.app/api/items`
- Frontend URL: `https://your-frontend-url.netlify.app`
- Test by accessing the frontend and adding an item with the Brand Name field

## Important Notes:
- Make sure MongoDB Atlas database is accessible from Railway
- The frontend must have the correct backend URL configured
- Monitor deployments for any errors in the platform dashboards
