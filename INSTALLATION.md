# Installation Guide - KIT Event Management System

This guide provides step-by-step instructions for setting up the KIT Event Management System.

## 📋 System Requirements

### Minimum Requirements
- **Node.js**: Version 18.0 or higher
- **npm**: Version 8.0 or higher
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 2GB free space
- **Browser**: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

### Recommended Development Environment
- **OS**: Windows 10/11, macOS 10.15+, or Ubuntu 20.04+
- **IDE**: Visual Studio Code with TypeScript and React extensions
- **Git**: Latest version for version control

## 🚀 Quick Start

### 1. Prerequisites Setup

#### Install Node.js
1. Visit [nodejs.org](https://nodejs.org/)
2. Download the LTS version for your operating system
3. Run the installer and follow the setup wizard
4. Verify installation:
```bash
node --version
npm --version
```

#### Install Git (if not already installed)
1. Visit [git-scm.com](https://git-scm.com/)
2. Download and install Git for your OS
3. Verify installation:
```bash
git --version
```

### 2. Project Setup

#### Clone the Repository
```bash
# Clone the project
git clone <repository-url>
cd kit-event-management

# Or download and extract the ZIP file
```

#### Install Dependencies
```bash
# Install all required packages
npm install

# This will install:
# - React and TypeScript dependencies
# - Tailwind CSS for styling
# - Supabase client for backend
# - All other required libraries
```

### 3. Database Setup (Supabase)

#### Create Supabase Account
1. Visit [supabase.com](https://supabase.com/)
2. Sign up for a free account
3. Create a new project
4. Note down your project URL and anon key

#### Configure Database
1. Go to your Supabase dashboard
2. Navigate to SQL Editor
3. Run the migration file provided in `supabase/migrations/`
4. This will create all necessary tables and security policies

### 4. Environment Configuration

#### Create Environment File
Create a `.env` file in the root directory:

```env
# Supabase Configuration
VITE_SUPABASE_URL=https://your-project-id.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key-here

# Razorpay Configuration (for payments)
VITE_RAZORPAY_KEY=rzp_test_your-key-here

# Optional: Custom Configuration
VITE_APP_NAME=KIT Event Management
VITE_APP_VERSION=1.0.0
```

#### Get Supabase Credentials
1. In your Supabase dashboard, go to Settings → API
2. Copy the Project URL and anon/public key
3. Paste them in your `.env` file

#### Setup Razorpay (Optional)
1. Create account at [razorpay.com](https://razorpay.com/)
2. Get your test API key from the dashboard
3. Add it to your `.env` file

### 5. Start Development Server

```bash
# Start the development server
npm run dev

# The application will be available at:
# http://localhost:5173
```

## 🔧 Advanced Configuration

### Database Migrations

If you need to run migrations manually:

```bash
# The migration file is located at:
# supabase/migrations/20250918175928_lucky_block.sql

# Copy and paste the SQL content into Supabase SQL Editor
# Or use Supabase CLI if installed
```

### Authentication Setup

The system comes with pre-configured authentication:

1. **Email/Password Authentication**: Enabled by default
2. **Email Confirmation**: Disabled for development
3. **Demo Users**: Created automatically

### Sample Data

The system includes sample data:
- **Events**: 6 sample events across different categories
- **Admin User**: admin@kit.ac.in / admin123
- **Student User**: student@kit.ac.in / student123

## 🏗️ Production Deployment

### Build for Production

```bash
# Create production build
npm run build

# This creates a 'dist' folder with optimized files
```

### Deploy to Vercel

1. Install Vercel CLI:
```bash
npm install -g vercel
```

2. Deploy:
```bash
vercel --prod
```

3. Set environment variables in Vercel dashboard

### Deploy to Netlify

1. Build the project:
```bash
npm run build
```

2. Upload the `dist` folder to Netlify
3. Set environment variables in Netlify dashboard

### Environment Variables for Production

```env
VITE_SUPABASE_URL=your-production-supabase-url
VITE_SUPABASE_ANON_KEY=your-production-anon-key
VITE_RAZORPAY_KEY=your-production-razorpay-key
```

## 🔍 Troubleshooting

### Common Issues

#### 1. Node.js Version Issues
```bash
# Check Node.js version
node --version

# If version is below 18, update Node.js
# Use nvm (Node Version Manager) for easy switching
```

#### 2. Package Installation Errors
```bash
# Clear npm cache
npm cache clean --force

# Delete node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

#### 3. Supabase Connection Issues
- Verify your Supabase URL and key in `.env`
- Check if your Supabase project is active
- Ensure RLS policies are properly set up

#### 4. Build Errors
```bash
# Check for TypeScript errors
npm run build

# Fix any type errors before deployment
```

### Getting Help

If you encounter issues:

1. **Check the Console**: Look for error messages in browser console
2. **Verify Environment**: Ensure all environment variables are set
3. **Database Connection**: Test Supabase connection in the dashboard
4. **Dependencies**: Ensure all packages are installed correctly

## 📚 Development Workflow

### Recommended Development Process

1. **Start Development Server**:
```bash
npm run dev
```

2. **Make Changes**: Edit files in the `src` directory

3. **Test Changes**: The development server auto-reloads

4. **Build for Production**:
```bash
npm run build
```

5. **Deploy**: Use your preferred deployment platform

### Code Structure

```
src/
├── components/          # Reusable UI components
├── pages/              # Page components
├── hooks/              # Custom React hooks
├── services/           # API and external services
├── types/              # TypeScript type definitions
├── utils/              # Utility functions
└── styles/             # CSS and styling files
```

## 🔐 Security Considerations

### Development Environment
- Use test API keys only
- Never commit `.env` files to version control
- Use HTTPS in production

### Production Environment
- Use production API keys
- Enable SSL/TLS certificates
- Set up proper CORS policies
- Monitor for security vulnerabilities

## 📊 Performance Optimization

### Development Tips
- Use React DevTools for debugging
- Monitor bundle size with build analyzer
- Optimize images and assets
- Implement code splitting for large applications

### Production Optimization
- Enable gzip compression
- Use CDN for static assets
- Implement caching strategies
- Monitor performance metrics

---

## 🎉 Success!

If you've followed all steps correctly, you should now have:

✅ A fully functional development environment  
✅ Database with sample data  
✅ Working authentication system  
✅ Payment integration ready  
✅ Admin and student dashboards  

**Next Steps:**
1. Explore the admin dashboard at `/admin`
2. Test student registration flow
3. Customize the application for your needs
4. Deploy to production when ready

For additional support, refer to the main README.md file or contact the development team.