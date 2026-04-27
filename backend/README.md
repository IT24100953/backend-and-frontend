# Backend - Item Manager Lab Test

## Prerequisites
- Node.js
- MongoDB (local or Atlas)

### Installing MongoDB on Windows
1. Download MongoDB Community Server from https://www.mongodb.com/try/download/community
2. Install the MSI file
3. During installation, choose "Complete" setup
4. After installation, MongoDB should be running as a service
5. Alternatively, use MongoDB Atlas (cloud): https://www.mongodb.com/atlas

## Setup
1. Open a terminal inside the backend folder.
2. Run:
   ```bash
   npm install
   ```
3. Copy `.env.example` to `.env` (if not present)
4. Update `MONGO_URI`:
   - For local MongoDB: `mongodb://localhost:27017/itemmanager`
   - For Atlas: `mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/itemmanager?retryWrites=true&w=majority`
5. Start the server:
   ```bash
   npm run dev
   ```

## API Endpoints
- `GET /api/items` - Get all items
- `GET /api/items/:id` - Get item by ID
- `POST /api/items` - Create new item
- `PUT /api/items/:id` - Update item
- `DELETE /api/items/:id` - Delete item
