# StudyNotion - EdTech Platform 🚀

<div align="center">

![StudyNotion Logo](images/mainpage.png)

### A fully functional EdTech platform to create, consume, and rate educational content.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Visit%20Site-brightgreen?style=for-the-badge)](https://d2iggsqshmb5f9.cloudfront.net/)
[![React](https://img.shields.io/badge/React-18.2.0-blue?style=for-the-badge&logo=react)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-18.x-green?style=for-the-badge&logo=node.js)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green?style=for-the-badge&logo=mongodb)](https://www.mongodb.com/)
[![AWS](https://img.shields.io/badge/AWS-Deployed-orange?style=for-the-badge&logo=amazon-aws)](https://aws.amazon.com/)

**🌐 Live Site: [https://d2iggsqshmb5f9.cloudfront.net](https://d2iggsqshmb5f9.cloudfront.net)**

</div>

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Live Demo](#live-demo)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Folder Structure](#folder-structure)
- [Architecture](#architecture)
- [API Design](#api-design)
- [Payment Integration](#payment-integration)
- [Deployment](#deployment)
- [Installation](#installation)
- [Configuration](#configuration)
- [Screenshots](#screenshots)

---

## 🎯 About the Project

**StudyNotion** is a fully functional EdTech platform built on the **MERN stack** that enables:

- 👨‍🎓 **Students** to browse, purchase, and consume high-quality courses
- 👨‍🏫 **Instructors** to create, manage, and monetize their educational content
- 💳 **Seamless payments** via Razorpay payment gateway
- ☁️ **Cloud media management** via Cloudinary for videos, images, and documents

The platform provides a seamless and interactive learning experience, making education more accessible and engaging for learners across the globe.

---

## 🌐 Live Demo

> **🔗 [https://d2iggsqshmb5f9.cloudfront.net](https://d2iggsqshmb5f9.cloudfront.net)**

The application is deployed on AWS using a fully serverless architecture:
- **Frontend** hosted on AWS S3 + CloudFront CDN
- **Backend** running on AWS Lambda + API Gateway
- **Database** on MongoDB Atlas (cloud)

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| ReactJS 18 | UI framework |
| Redux Toolkit | State management |
| Tailwind CSS | Styling |
| React Router DOM | Client-side routing |
| Axios | HTTP requests |
| React Hook Form | Form handling |
| Chart.js | Instructor analytics |
| Swiper.js | Course carousels |
| React Markdown | Render markdown content |
| Video React | Course video player |

### Backend
| Technology | Purpose |
|---|---|
| Node.js | Runtime environment |
| Express.js | Web framework |
| MongoDB + Mongoose | Database + ODM |
| JWT | Authentication |
| Bcrypt | Password hashing |
| Nodemailer | Email service (OTP, notifications) |
| Cloudinary | Media storage (videos, images) |
| Razorpay | Payment gateway |
| express-fileupload | File upload handling |

### DevOps & Cloud
| Service | Purpose |
|---|---|
| AWS Lambda | Serverless backend hosting |
| AWS API Gateway | REST API routing |
| AWS S3 | Frontend static hosting |
| AWS CloudFront | CDN for fast global delivery |
| AWS SAM | Infrastructure as code |
| MongoDB Atlas | Cloud database |

---

## ✨ Features

### For Students
- 🔐 Secure signup, login with OTP email verification
- 🔑 Forgot password / reset password flow
- 📚 Browse all available courses with descriptions and ratings
- 🛒 Add courses to cart and checkout
- 💳 Purchase courses via **Razorpay payment gateway**
- 🎥 Watch course videos with progress tracking
- ⭐ Rate and review courses
- 👤 Manage personal profile and account settings
- 📋 View enrolled courses dashboard

### For Instructors
- 📊 Dashboard with course performance overview
- 📈 Detailed insights — views, enrollments, revenue
- ➕ Create, edit, and delete courses
- 🗂️ Manage course sections and subsections
- 🖼️ Upload course thumbnails and videos via Cloudinary
- 💰 Set course pricing
- 👥 View student enrollments per course

### Platform
- 📧 Automated email notifications (OTP, payment confirmation, welcome email)
- 📝 Markdown support for rich course content
- 🌐 Fully responsive design
- ⚡ Fast global delivery via CloudFront CDN

---

## 📁 Folder Structure

```
STUDY-NOTION-MASTER/
│
├── 📁 server/                          # Backend (Node.js + Express)
│   ├── 📁 config/
│   │   ├── cloudinary.js               # Cloudinary configuration
│   │   └── database.js                 # MongoDB connection
│   ├── 📁 controllers/                 # Route handler logic
│   │   ├── Auth.js                     # Authentication controllers
│   │   ├── Course.js                   # Course CRUD controllers
│   │   ├── Payment.js                  # Razorpay payment controllers
│   │   ├── Profile.js                  # User profile controllers
│   │   └── ...
│   ├── 📁 mail/                        # Email templates
│   │   └── templates/
│   ├── 📁 middlewares/
│   │   └── auth.js                     # JWT auth middleware
│   ├── 📁 models/                      # MongoDB schemas
│   │   ├── Category.js
│   │   ├── Course.js
│   │   ├── CourseProgress.js
│   │   ├── OTP.js
│   │   ├── Profile.js
│   │   ├── RatingAndReview.js
│   │   ├── Section.js
│   │   ├── SubSection.js
│   │   └── User.js
│   ├── 📁 routes/                      # Express route definitions
│   │   ├── User.js
│   │   ├── Profile.js
│   │   ├── Course.js
│   │   ├── Payments.js
│   │   └── Contact.js
│   ├── 📁 utils/
│   │   ├── imageUploader.js            # Cloudinary upload helper
│   │   ├── mailSender.js               # Nodemailer helper
│   │   └── secToDuration.js            # Duration formatter
│   ├── .env                            # Environment variables
│   ├── index.js                        # Express app entry point
│   ├── template.yaml                   # AWS SAM configuration
│   ├── samconfig.toml                  # SAM deploy settings
│   └── package.json
│
├── 📁 src/                             # Frontend (React)
│   ├── 📁 assets/                      # Images, icons, fonts
│   ├── 📁 components/                  # Reusable UI components
│   ├── 📁 data/                        # Static data & constants
│   ├── 📁 hooks/                       # Custom React hooks
│   ├── 📁 pages/                       # Page-level components
│   ├── 📁 reducer/                     # Redux store setup
│   ├── 📁 services/
│   │   ├── 📁 operations/              # API call functions
│   │   ├── apiconnector.js             # Axios instance setup
│   │   ├── apis.js                     # All API endpoint URLs
│   │   └── formatDate.js
│   ├── 📁 slices/                      # Redux state slices
│   ├── 📁 utils/                       # Utility functions
│   ├── App.js                          # Root component
│   └── index.js                        # React entry point
│
├── 📁 public/                          # Static public assets
│   ├── index.html
│   └── robots.txt
│
├── 📁 images/                          # README images
├── .env                                # Frontend environment variables
├── package.json                        # Frontend dependencies
├── tailwind.config.js                  # Tailwind CSS config
└── README.md
```

---

## 🏗️ Architecture

```
                        ┌─────────────────────┐
                        │      Students /      │
                        │     Instructors      │
                        └────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │   AWS CloudFront (CDN)   │
                    │   Global fast delivery   │
                    └────────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │       AWS S3 Bucket      │
                    │   React Static Frontend  │
                    └────────────┬────────────┘
                                 │ API Calls
                    ┌────────────▼────────────┐
                    │    AWS API Gateway       │
                    │    REST API Routing      │
                    └────────────┬────────────┘
                                 │
                    ┌────────────▼────────────┐
                    │      AWS Lambda          │
                    │  Node.js + Express App   │
                    └──┬──────────────────┬───┘
                       │                  │
          ┌────────────▼───┐    ┌────────▼────────┐
          │ MongoDB Atlas  │    │   Cloudinary     │
          │ (Database)     │    │ (Media Storage)  │
          └────────────────┘    └─────────────────┘
```

---

## 🔌 API Design

The API follows **REST architecture** using standard HTTP methods:

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/v1/auth/signup` | Register new user |
| POST | `/api/v1/auth/login` | User login |
| POST | `/api/v1/auth/sendotp` | Send OTP to email |
| POST | `/api/v1/auth/reset-password` | Reset password |
| GET | `/api/v1/course/getAllCourses` | Fetch all courses |
| POST | `/api/v1/course/createCourse` | Create new course |
| POST | `/api/v1/payment/capturePayment` | Initiate payment |
| POST | `/api/v1/payment/verifyPayment` | Verify payment |
| GET | `/api/v1/profile/getUserDetails` | Get user profile |
| PUT | `/api/v1/profile/updateProfile` | Update profile |

---

## 💳 Payment Integration

StudyNotion uses **Razorpay** as its payment gateway for secure course purchases.

### Payment Flow
```
Student clicks "Buy Now"
        │
        ▼
Backend creates Razorpay Order
        │
        ▼
Razorpay Payment Modal opens
        │
        ▼
Student enters card / UPI / wallet details
        │
        ▼
Payment processed by Razorpay
        │
        ▼
Backend verifies payment signature
        │
        ▼
Student enrolled in course ✅
        │
        ▼
Confirmation email sent via Nodemailer
```

### Supported Payment Methods
- 💳 Credit / Debit Cards
- 📱 UPI (GPay, PhonePe, Paytm)
- 🏦 Net Banking
- 👛 Wallets

---

## ☁️ Deployment

This project is deployed on **AWS Free Tier** using a fully serverless architecture — no servers to manage!

| Component | Service | Cost |
|---|---|---|
| Frontend | S3 + CloudFront | Free tier |
| Backend | Lambda + API Gateway | Free tier |
| Database | MongoDB Atlas M0 | Always free |
| Media | Cloudinary | Free tier |
| **Total** | | **₹0 / month** |

### Deploy Backend
```bash
cd server
sam build
sam deploy --guided
```

### Deploy Frontend
```bash
npm run build
aws s3 sync ./build s3://your-bucket-name
aws cloudfront create-invalidation --distribution-id YOUR_ID --paths "/*"
```

---

## ⚙️ Installation

### Prerequisites
- Node.js v18+
- npm v8+
- MongoDB Atlas account
- Cloudinary account
- Razorpay account

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/study-notion.git
cd study-notion
```

### 2. Install frontend dependencies
```bash
npm install
```

### 3. Install backend dependencies
```bash
cd server
npm install
```

---

## 🔧 Configuration

### Frontend `.env` (root folder)
```env
REACT_APP_BASE_URL=http://localhost:4000/api/v1
```

### Backend `.env` (server folder)
```env
MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/Study-Notion
JWT_SECRET=your_jwt_secret_key

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

RAZORPAY_KEY_ID=rzp_test_xxxxxxxxxxxx
RAZORPAY_SECRET=your_razorpay_secret

MAIL_HOST=smtp.gmail.com
MAIL_USER=your_email@gmail.com
MAIL_PASS=your_app_password
```

### Run Locally
```bash
# Run backend
cd server
npm run dev

# Run frontend (new terminal)
cd ..
npm start
```

Access at: `http://localhost:3000`

---

## 📸 Screenshots

### Home Page
![Home Page](images/mainpage.png)

### Database Schema
![Schema](images/schema.png)

### Architecture Diagram
![Architecture](images/architecture.png)

---

## 👨‍💻 Author

Built and deployed with ❤️ using the MERN stack on AWS.

---

## 📄 License

This project is for educational purposes.
