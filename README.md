# CareerBridge – Job Portal Platform

CareerBridge is a full-stack job and hiring portal where candidates can search and apply for jobs, manage their profiles and resumes, while recruiters can register companies, post jobs, and manage applicants. The application uses cookie-based JWT authentication with protected routes on both the backend and frontend.

## Technologies Used

- **Backend:** Node.js, Express.js, MongoDB (Mongoose), JWT  
- **Frontend:** React (Vite), Redux Toolkit, Redux Persist, React Router, Tailwind CSS (v4), shadcn/ui, Framer Motion  
- **File & Media:** Multer (in-memory storage), Cloudinary  
- **Tooling:** ESLint, Nodemon  


## Features

- **Authentication:** Role-based login and registration (`student` / `recruiter`) using cookie-based JWT sessions.  
- **Candidate Module:** Profile management, resume upload and viewing, job search and filtering, job applications, and applied job tracking.  
- **Recruiter Module:** Company registration and updates (with logo upload), job posting and management, applicant viewing, and application status updates.  
- **Job Management:** Post jobs, browse jobs with keyword filters, view job details, and track applications.  
- **File Uploads:** Secure resume and company asset uploads using Multer and Cloudinary. 
