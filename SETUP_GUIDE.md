# Item Manager MERN Application - Complete Setup & Deployment Guide

## Project Status ✅

- ✅ Backend & Frontend created
- ✅ Brand Name field added
- ✅ MongoDB Atlas connected
- ✅ Code pushed to GitHub
- 🔄 Ready for Railway deployment

## Repository Information

**GitHub Repository:** https://github.com/IT24100953/backend-and-frontend

## MongoDB Configuration

**Connection String:** `mongodb+srv://admin:migara17%40%24_migara17%40%24_@cluster0.chaiiwr.mongodb.net/itemmanager?retryWrites=true&w=majority`

## Local Development

### Backend Setup
```bash
cd backend
npm install
npm run dev
```
Backend runs on: http://localhost:5000

### Frontend Setup
```bash
cd frontend
npm install
npm run dev
```
Frontend runs on: http://localhost:5173

## Deployment to Railway

### Backend Deployment Steps:

1. **Go to Railway Dashboard**
   - Visit https://railway.app
   - Sign in (create account if needed)

2. **Create Backend Project**
   - Click "New Project"
   - Select "Deploy from GitHub repo"
   - Authorize GitHub if needed
   - Select `IT24100953/backend-and-frontend` repository

3. **Configure Backend**
   - Railway auto-detects Node.js backend
   - Go to Variables tab and add:
     - `PORT`: `5000`
     - `MONGO_URI`: `mongodb+srv://admin:migara17%40%24_migara17%40%24_@cluster0.chaiiwr.mongodb.net/itemmanager?retryWrites=true&w=majority`

4. **Deploy**
   - Click "Deploy" button
   - Wait for deployment to complete
   - Copy the generated URL (e.g., `https://item-manager-backend.up.railway.app`)

5. **Test Backend**
   - Visit: `https://item-manager-backend.up.railway.app/api/items`
   - Should return an empty array or list of items

### Frontend Deployment to Railway/Netlify:

#### Option A: Deploy Frontend to Railway

1. **Create Frontend Service in Same Project**
   - In the same Railway project, click "New Service"
   - Select "Deploy from GitHub repo"
   - Select same repository

2. **Configure Frontend**
   - Build command: `npm run build`
   - Start command: `npm run preview`
   - Add environment variable:
     - `VITE_API_URL`: `https://item-manager-backend.up.railway.app/api`

3. **Deploy**
   - Railway will deploy automatically

#### Option B: Deploy Frontend to Netlify (Recommended for Frontend)

1. **Go to Netlify**
   - Visit https://netlify.com
   - Sign in or create account

2. **Create New Site**
   - Click "Add new site" → "Import an existing project"
   - Authorize GitHub
   - Select repository `IT24100953/backend-and-frontend`

3. **Configure Build Settings**
   - Owner: Your GitHub username
   - Branch to deploy: `main`
   - Build command: `cd frontend && npm run build`
   - Publish directory: `frontend/dist`
   - Drag and drop option: Select frontend folder

4. **Set Environment Variables**
   - Click "Site settings" → "Build & deploy" → "Environment"
   - Click "Edit variables"
   - Add: `VITE_API_URL` = `https://item-manager-backend.up.railway.app/api`

5. **Deploy**
   - Netlify will build and deploy automatically
   - Get your frontend URL (e.g., `https://item-manager-frontend.netlify.app`)

## Verification Checklist

After deployment, verify:
- [ ] Backend API is accessible: `https://your-backend-url/api/items`
- [ ] Frontend loads: `https://your-frontend-url`
- [ ] Navigation works (Home, Add Item pages)
- [ ] Can add a new item with Brand Name
- [ ] Item appears on Home page with Brand Name
- [ ] Can edit items
- [ ] Can delete items
- [ ] CORS working (no browser errors)

## Files Structure

```
WMT_LabTest_Project/
├── backend/
│   ├── models/Item.js (contains brand field)
│   ├── controllers/itemController.js
│   ├── routes/itemRoutes.js
│   ├── server.js
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── ItemForm.jsx (has Brand Name field)
│   │   │   ├── ItemCard.jsx (displays Brand Name)
│   │   │   └── Navbar.jsx
│   │   ├── pages/
│   │   │   ├── HomePage.jsx
│   │   │   ├── AddItemPage.jsx
│   │   │   └── EditItemPage.jsx
│   │   ├── api/itemApi.js
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   └── package.json
├── README.md
└── DEPLOYMENT_GUIDE.md
```

## New Features Added

### Brand Name Field
- **Backend**: Added `brand` field to Item schema in `models/Item.js`
- **Frontend Form**: Added Brand Name input in `components/ItemForm.jsx`
- **Display**: Brand Name shown in `components/ItemCard.jsx`
- **CRUD Operations**: Brand Name works with Add, Read, Update, Delete operations

## API Endpoints

```
GET    /api/items           - Get all items
GET    /api/items/:id       - Get item by ID
POST   /api/items           - Create new item
PUT    /api/items/:id       - Update item
DELETE /api/items/:id       - Delete item
```

## Request/Response Examples

### Create Item (POST /api/items)
```json
{
  "name": "Laptop",
  "brand": "Dell",
  "category": "Electronics",
  "price": 999,
  "description": "High-performance laptop",
  "imageUrl": "https://example.com/image.jpg"
}
```

### Response
```json
{
  "_id": "507f1f77bcf86cd799439011",
  "name": "Laptop",
  "brand": "Dell",
  "category": "Electronics",
  "price": 999,
  "description": "High-performance laptop",
  "imageUrl": "https://example.com/image.jpg",
  "createdAt": "2024-04-27T10:00:00Z",
  "updatedAt": "2024-04-27T10:00:00Z",
  "__v": 0
}
```

## Deployment Notes

- Total files modified: 3 (Item.js, ItemForm.jsx, ItemCard.jsx)
- MongoDB: Atlas cloud database
- Backend platform: Railway
- Frontend platform: Netlify or Railway
- CI/CD: GitHub integration with Railway/Netlify

## Next Steps

1. Deploy backend to Railway
2. Get backend URL
3. Update frontend VITE_API_URL environment variable
4. Deploy frontend to Netlify/Railway
5. Test all CRUD operations on live site
6. Capture screenshots for submission
