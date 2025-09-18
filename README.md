# KIT Event Management System

A comprehensive event management platform for Kanpur Institute of Technology, built with React, TypeScript, and Supabase.

## 🚀 Features

### Public Website
- Modern, responsive design showcasing all institute events
- Event categorization (Technical, Cultural, Sports, Workshops, Seminars, Competitions)
- Advanced search and filtering capabilities
- Event details with venue, timing, and registration information
- Mobile-optimized interface

### Student Portal
- Secure user authentication and registration
- Personal dashboard with registration history
- Multi-event registration capability
- Payment integration with Razorpay
- Profile management and event tracking
- Excel export of personal registration data

### Admin Dashboard
- Comprehensive event management (Create, Read, Update, Delete)
- User management and role-based access control
- Registration monitoring and analytics
- Payment transaction tracking
- Data export capabilities (Excel format)
- Real-time statistics and reporting
- Visual analytics with charts and graphs

### Payment System
- Secure Razorpay integration for online payments
- Multiple payment methods (Cards, UPI, Net Banking)
- Transaction tracking and status monitoring
- Automated payment confirmation
- Refund management capabilities

## 🛠️ Technology Stack

### Frontend
- **React 18** with TypeScript for type safety
- **Tailwind CSS** for modern, responsive styling
- **React Router** for client-side routing
- **React Hook Form** with Zod validation
- **Recharts** for data visualization
- **Lucide React** for consistent iconography
- **Date-fns** for date manipulation

### Backend & Database
- **Supabase** for backend services and PostgreSQL database
- **Row Level Security (RLS)** for data protection
- **Real-time subscriptions** for live updates
- **Automated triggers** for data consistency

### Additional Libraries
- **XLSX** for Excel file generation and export
- **html2canvas & jsPDF** for PDF generation
- **Razorpay** for payment processing

## 📋 Prerequisites

- Node.js 18+ and npm
- Supabase account and project
- Razorpay account (for payment integration)

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd kit-event-management
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Configuration
Create a `.env` file in the root directory:
```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
VITE_RAZORPAY_KEY=your_razorpay_key
```

### 4. Database Setup
The database schema is automatically created through Supabase migrations. The system includes:

#### Tables:
- **users**: Student and admin profiles
- **events**: Event information and details
- **registrations**: Event registration records
- **payments**: Payment transaction history

#### Security:
- Row Level Security (RLS) enabled on all tables
- Role-based access policies
- Secure authentication flow

### 5. Start Development Server
```bash
npm run dev
```

The application will be available at `http://localhost:5173`

## 👥 User Roles & Access

### Students
- Browse and search events
- Register for multiple events
- Make secure payments
- View registration history
- Export personal data
- Update profile information

### Administrators
- Full event management capabilities
- User account management
- Registration and payment monitoring
- Comprehensive reporting and analytics
- Data export functionality
- System configuration

## 🔐 Demo Credentials

### Admin Access
- **Email**: admin@kit.ac.in
- **Password**: admin123

### Student Access
- **Email**: student@kit.ac.in
- **Password**: student123

## 📊 Database Schema

### Users Table
```sql
- id (UUID, Primary Key)
- email (Text, Unique)
- full_name (Text)
- student_id (Text, Unique)
- phone (Text)
- course (Text)
- year (Integer)
- role (Enum: student/admin)
- created_at (Timestamp)
```

### Events Table
```sql
- id (UUID, Primary Key)
- title (Text)
- description (Text)
- category (Enum)
- date (Date)
- time (Text)
- venue (Text)
- registration_fee (Numeric)
- max_participants (Integer)
- current_participants (Integer)
- registration_deadline (Date)
- image_url (Text)
- rules (Text Array)
- contact_email (Text)
- contact_phone (Text)
- is_active (Boolean)
- created_at/updated_at (Timestamps)
```

### Registrations Table
```sql
- id (UUID, Primary Key)
- user_id (UUID, Foreign Key)
- event_id (UUID, Foreign Key)
- registration_date (Timestamp)
- payment_status (Enum)
- payment_id (Text)
- amount_paid (Numeric)
```

## 🔧 Key Features Implementation

### Authentication System
- Supabase Auth with email/password
- Role-based access control
- Protected routes and components
- Session management

### Payment Integration
- Razorpay payment gateway
- Secure transaction processing
- Payment status tracking
- Automated confirmations

### Data Export
- Excel file generation using XLSX
- Comprehensive data formatting
- Multiple export formats
- Automated file naming

### Real-time Updates
- Live participant count updates
- Real-time registration status
- Instant payment confirmations
- Dynamic event availability

## 📱 Responsive Design

The application is fully responsive and optimized for:
- Desktop computers (1920px+)
- Laptops (1024px - 1919px)
- Tablets (768px - 1023px)
- Mobile phones (320px - 767px)

## 🔒 Security Features

- Row Level Security (RLS) on all database tables
- Input validation and sanitization
- Secure payment processing
- Protected API endpoints
- Role-based access control
- SQL injection prevention

## 📈 Performance Optimizations

- Code splitting and lazy loading
- Image optimization
- Efficient database queries
- Caching strategies
- Minimized bundle size

## 🚀 Deployment

### Build for Production
```bash
npm run build
```

### Deploy to Vercel/Netlify
1. Connect your repository
2. Set environment variables
3. Deploy automatically on push

### Supabase Configuration
1. Set up your Supabase project
2. Run database migrations
3. Configure authentication settings
4. Set up RLS policies

## 📞 Support & Contact

For technical support or queries:
- **Email**: support@kit.ac.in
- **Phone**: +91 512 123 4567
- **Website**: https://kit.ac.in

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📝 Changelog

### Version 1.0.0
- Initial release with full event management system
- Student registration and payment integration
- Admin dashboard with comprehensive features
- Responsive design and mobile optimization
- Excel export functionality
- Real-time updates and notifications

---

**Developed with ❤️ for Kanpur Institute of Technology**