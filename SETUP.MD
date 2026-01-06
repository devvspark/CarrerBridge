## Setup Guide

Step-by-step instructions to run the project locally on Windows (PowerShell) or any Node-friendly environment.

### 1) Prerequisites
- Node.js 18+ (20.x recommended) and npm.
- MongoDB instance/URI (local or hosted).
- Cloudinary account for file storage.
- Optional: Postman/Insomnia for API testing.

### 2) Environment Variables

Create `backend2/.env`:
```
PORT=8000
MONGO_URI=mongodb://127.0.0.1:27017/careerbridge   # or your hosted URI
SECRET_KEY=change_me_to_a_strong_secret

# Cloudinary
CLOUD_NAME=your_cloud_name
API_KEY=your_api_key
API_SECRET=your_api_secret
```

Create `frontend2/.env` (point to your API host):
```
VITE_USER_API_URL=http://localhost:8000/api/v1/user
VITE_JOB_API_URL=http://localhost:8000/api/v1/job
VITE_APPLICATION_API_URL=http://localhost:8000/api/v1/application
VITE_COMPANY_API_URL=http://localhost:8000/api/v1/company
```

### 3) Install Dependencies
- Backend: `cd backend2 && npm install`
- Frontend: `cd frontend2 && npm install`

### 4) Run in Development
Open two terminals:
- Backend API (with auto-reload): `cd backend2 && npm run dev`
- Frontend UI: `cd frontend2 && npm run dev`

Access the app at `http://localhost:5173`. API listens on `http://localhost:8000` by default.

### 5) CORS & Cookies
- CORS is pre-configured to allow `http://localhost:5173` and `https://carrer-bridge-phi.vercel.app` in `backend2/index.js`. Add your origin if different.
- Auth uses HTTP-only cookies; keep `credentials: true` on client requests (already handled in the app).

### 6) File Uploads
- Uploads use Multer (memory) → Cloudinary. Ensure Cloudinary env vars are set; otherwise uploads will fail.
- Resume/profile/company uploads expect the form field name `file`.

### 7) Common Verification Steps
- Hit `GET http://localhost:8000/api/v1/job/get` with an authenticated session to confirm DB connection.
- Register/login via UI (`/signup`, `/login`) to verify cookies and frontend-backend connectivity.
- Post a job (recruiter role) and apply as a student to exercise the full flow.

### 8) Production Notes
- Set strong `SECRET_KEY` and production Mongo URI.
- Update CORS allowed origins in `backend2/index.js`.
- Point frontend `VITE_*` env vars at the deployed API.
- Serve the frontend build via `npm run build && npm run preview` or your hosting of choice.

