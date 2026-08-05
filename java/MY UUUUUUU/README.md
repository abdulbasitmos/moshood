# Yusmad Catering Services - Professional Catering Website

A complete, full-featured professional catering website with user authentication, booking system, and admin dashboard. Built with pure HTML, CSS, and JavaScript using localStorage for data persistence.

## 🌟 Project Overview

**Business Name:** Yusmad Catering Services  
**Business Type:** Luxury Catering & Event Services  
**Design Style:** Modern Luxury with Gold/Black/White Color Scheme  
**Responsive:** Fully responsive for Mobile & Desktop devices

## ✨ Features Completed

### 🎨 Frontend Features (All Implemented)
- ✅ **Sticky Navbar** - Transparent on top, solid on scroll with mobile hamburger menu
- ✅ **Loading Animation** - Luxury gold spinner (1.5 seconds)
- ✅ **Welcome Popup** - First-visit popup with special offer
- ✅ **Live Search Bar** - Search through services/content
- ✅ **Multi-Language Switch** - English/Malay/Arabic toggle
- ✅ **Page Animations** - AOS (Animate On Scroll) library integrated
- ✅ **Back-to-Top Button** - Smooth scrolling floating gold button
- ✅ **Floating WhatsApp Button** - Opens WhatsApp chat (+60123456789)
- ✅ **AI Chat Widget** - Simulated chat assistant with predefined responses
- ✅ **Contact Form** - Saves messages to localStorage
- ✅ **Responsive Design** - Mobile-first CSS with breakpoints

### 📄 Pages Implemented (11 Pages)

#### Public Pages
1. **index.html** - Home Page
   - Hero section with full-screen background
   - Services preview (4 services)
   - About snippet section
   - Gallery preview (6 images)
   - Testimonials carousel (3 testimonials)
   - Animated stats counter (Events, Clients, Years, Team)
   - CTA section
   - Complete footer with links

2. **about.html** - About Page
   - Company story with 15 years history
   - Mission & Vision cards
   - Team members section (4 team members)
   - Why Choose Us section (6 features)

3. **services.html** - Services & Packages
   - 4 pricing packages (Basic/Standard/Premium/Luxury)
   - Detailed service cards (Wedding/Birthday/Corporate/Outdoor)
   - Package comparison table
   - FAQ accordion (6 questions)

4. **gallery.html** - Gallery
   - Filterable image gallery (All/Weddings/Birthdays/Corporate/Outdoor)
   - 12+ placeholder images from picsum.photos
   - Lightbox popup on image click
   - Masonry grid layout

5. **contact.html** - Contact Page
   - Contact form (saves to localStorage)
   - Contact info cards (Address, Phone, Email, Hours)
   - Google Maps embed
   - Success message notification

#### User System Pages
6. **signup.html** - User Registration
   - Full name, email, phone, password fields
   - Password strength indicator (Weak/Medium/Strong)
   - Form validation (email format, password match, phone format)
   - Saves to localStorage with btoa() password encoding
   - Auto-redirect to dashboard after registration

7. **login.html** - User Login
   - Email + Password authentication
   - Remember me checkbox
   - Validates against localStorage users
   - Session management via sessionStorage
   - Forgot password link

8. **dashboard.html** - User Dashboard (Protected)
   - Welcome message with user name
   - Stats cards (Total Bookings, Upcoming Events, Completed)
   - Profile section (view profile info)
   - Booking history table with status badges
   - Cancel booking functionality
   - Logout button

9. **booking.html** - Booking Page (Protected)
   - Event type selection (Wedding/Birthday/Corporate/Outdoor)
   - Event date picker (minimum tomorrow)
   - Number of guests input
   - Location field
   - Package selection (Basic/Standard/Premium/Luxury)
   - Special requests textarea
   - Package info display with pricing
   - Guest validation against package capacity
   - Success modal with booking ID
   - Saves to localStorage

#### Admin System Pages
10. **admin-login.html** - Admin Login
    - Secure admin authentication
    - Default credentials displayed
    - Admin session management
    - Separate from user login

11. **admin-dashboard.html** - Admin Dashboard (Protected)
    - Statistics cards (Total Users, Bookings, Monthly, Revenue)
    - Tabbed interface (Bookings/Users/Messages/Analytics)
    - **Bookings Management:**
      - View all bookings
      - Update status (Pending/Confirmed/Completed/Cancelled)
      - Delete bookings
    - **Users Management:**
      - View all registered users
      - Delete users (cascade delete bookings)
    - **Contact Messages:**
      - View all contact form submissions
    - **Analytics:**
      - Most requested service
      - Monthly bookings chart (Chart.js)
      - Revenue summary
      - Average booking value

## 🗄️ Database Structure (localStorage)

### Collections:

```javascript
// Admin Credentials
yusmad_admin: {
    email: "admin@yusmad.com",
    password: btoa("Admin@2024")
}

// Users Array
yusmad_users: [{
    id: string,
    fullName: string,
    email: string,
    phone: string,
    password: string (btoa encoded),
    createdAt: ISO date string,
    status: "active"
}]

// Bookings Array
yusmad_bookings: [{
    id: string,
    userId: string,
    userName: string,
    userEmail: string,
    userPhone: string,
    eventType: "Wedding" | "Birthday" | "Corporate" | "Outdoor",
    eventDate: date string,
    guests: number,
    location: string,
    package: "Basic" | "Standard" | "Premium" | "Luxury",
    specialRequests: string,
    status: "Pending" | "Confirmed" | "Completed" | "Cancelled",
    totalAmount: number,
    createdAt: ISO date string
}]

// Messages Array
yusmad_messages: [{
    id: string,
    name: string,
    email: string,
    phone: string,
    subject: string,
    message: string,
    createdAt: ISO date string,
    read: boolean
}]

// Analytics Object
yusmad_analytics: {
    totalRevenue: number,
    monthlyData: {
        "YYYY-MM": {
            bookings: number,
            revenue: number
        }
    }
}
```

## 💰 Pricing Packages

| Package | Price | Guests | Main Dishes | Features |
|---------|-------|--------|-------------|----------|
| **Basic** | RM 1,500 | Up to 50 | 3 | Basic setup, 2 staff |
| **Standard** | RM 3,000 | Up to 100 | 5 | Elegant setup, decoration, 4 staff |
| **Premium** | RM 6,000 | Up to 200 | 7 | Luxury setup, live cooking, 6 staff |
| **Luxury** | RM 12,000 | Up to 500 | 10+ | Complete decoration, coordinator, 10+ staff |

## 🔐 Security Features

- **Password Encoding:** btoa() encoding for passwords (in production, use bcrypt)
- **Session Management:** sessionStorage for user/admin sessions
- **Protected Pages:** Authentication check on dashboard and booking pages
- **Role Separation:** Separate admin and user authentication
- **Input Validation:** Client-side validation for all forms
- **XSS Prevention:** Text sanitization for user inputs

## 🎨 Design & Styling

### Color Palette:
- **Primary Gold:** #D4AF37
- **Gold Light:** #F0D060  
- **Gold Dark:** #8B7322
- **Black:** #0A0A0A
- **Black Light:** #1A1A1A
- **White:** #FFFFFF

### Typography:
- **Headings:** Playfair Display (Serif)
- **Body Text:** Lato (Sans-serif)

### Effects:
- Glassmorphism cards with backdrop-filter blur
- Gold gradient effects on buttons and headings
- Smooth transitions and hover effects
- AOS animations on scroll

## 📱 Responsive Design

- **Mobile-first approach**
- **Breakpoint:** 768px for tablet/mobile
- **Hamburger menu** for mobile navigation
- **Grid layouts** adjust to single column on mobile
- **Touch-friendly** buttons and interactive elements

## 📞 Contact Information

- **WhatsApp:** +60123456789
- **Email:** info@yusmadcatering.com
- **Booking Email:** booking@yusmadcatering.com
- **Address:** Jalan Sultan Ismail, Kuala Lumpur, 50250 Malaysia
- **Hours:** Monday - Sunday: 9:00 AM - 10:00 PM

## 🚀 Getting Started

### User Flow:
1. Visit **index.html** (Home page)
2. Browse services, gallery, and about pages
3. Click **Sign Up** to create an account
4. **Login** with credentials
5. Access **Dashboard** to view profile and bookings
6. Create **New Booking** via booking page
7. View booking history and cancel if needed

### Admin Flow:
1. Visit **admin-login.html**
2. Login with credentials:
   - Email: `admin@yusmad.com`
   - Password: `Admin@2024`
3. Access **Admin Dashboard**
4. Manage bookings, users, and view analytics
5. Update booking statuses
6. View contact messages
7. Monitor revenue and statistics

## 📊 Analytics Features

- **Total Users:** Count of registered users
- **Total Bookings:** All-time booking count
- **Monthly Bookings:** Current month bookings
- **Total Revenue:** Sum of all confirmed bookings
- **Most Requested Service:** Most popular event type
- **Monthly Chart:** Visual representation using Chart.js
- **Average Booking Value:** Revenue per booking

## 🔧 Technical Stack

### Frontend:
- **HTML5** - Semantic markup
- **CSS3** - Custom styling with CSS variables
- **JavaScript (Vanilla)** - No frameworks, pure JS
- **LocalStorage** - Client-side data persistence
- **SessionStorage** - Session management

### Libraries (CDN):
- **Font Awesome 6.4.0** - Icons
- **Google Fonts** - Playfair Display & Lato
- **AOS 2.3.1** - Animate On Scroll
- **Chart.js** - Analytics charts

### Images:
- **Picsum.photos** - Placeholder images (random)

## 📋 Features Not Yet Implemented

1. **Profile Editing** - Edit user profile functionality
2. **Password Reset** - Forgot password email flow
3. **Email Notifications** - Actual email sending for confirmations
4. **Payment Gateway** - Online payment integration
5. **Image Upload** - User-uploaded event images
6. **Advanced Search** - Full-text search functionality
7. **Real-time Updates** - WebSocket for live notifications
8. **PDF Invoices** - Downloadable booking invoices
9. **Multiple Languages** - Full translation system
10. **Calendar Integration** - Export to Google Calendar

## 🎯 Recommended Next Steps

1. **Backend Integration:**
   - Replace localStorage with REST API
   - Implement proper database (MongoDB/PostgreSQL)
   - Add server-side authentication with JWT

2. **Email System:**
   - Integrate email service (SendGrid/Mailgun)
   - Send booking confirmations
   - Password reset emails

3. **Payment Integration:**
   - Add payment gateway (Stripe/PayPal)
   - Online deposit system
   - Invoice generation

4. **Advanced Features:**
   - Menu customization tool
   - Real-time availability checker
   - Photo gallery upload
   - Review and rating system

5. **SEO & Performance:**
   - Add meta tags and structured data
   - Image optimization
   - Lazy loading
   - CDN integration

## 📝 File Structure

```
/
├── index.html              # Home page
├── about.html              # About page
├── services.html           # Services & packages
├── gallery.html            # Image gallery
├── contact.html            # Contact form
├── signup.html             # User registration
├── login.html              # User login
├── dashboard.html          # User dashboard
├── booking.html            # Booking form
├── admin-login.html        # Admin login
├── admin-dashboard.html    # Admin panel
└── README.md              # This file
```

## 🎭 Demo Credentials

### User Account:
- Create new account via **signup.html**
- Or use any registered user

### Admin Account:
- **Email:** admin@yusmad.com
- **Password:** Admin@2024

## 🌐 Browser Compatibility

- ✅ Chrome (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)
- ⚠️ IE11 (limited support)

## 📄 License

This project is created for Yusmad Catering Services.  
© 2024 Yusmad Catering Services. All rights reserved.

## 👨‍💻 Development Notes

- All files are self-contained with embedded CSS and JavaScript
- No build process required
- No external dependencies except CDN libraries
- Data persists in browser localStorage
- Clearing browser data will reset all data
- Works offline (except CDN resources)

## 🐛 Known Limitations

1. **Data Persistence:** LocalStorage only - data is browser-specific
2. **Security:** Client-side authentication (not production-ready)
3. **Scalability:** Limited by localStorage 5-10MB limit
4. **Multi-device:** Cannot sync across devices
5. **Email:** No actual email sending (simulated)
6. **File Upload:** No server to store uploaded files
7. **Real-time:** No real-time updates between users

## ✅ Testing Checklist

- ✅ User registration works
- ✅ User login authentication works
- ✅ Booking creation saves correctly
- ✅ Admin can view all bookings
- ✅ Admin can update booking status
- ✅ Contact form saves messages
- ✅ Dashboard displays correct statistics
- ✅ Mobile responsive on all pages
- ✅ All navigation links work
- ✅ Chat widget responds correctly
- ✅ Gallery filter and lightbox work
- ✅ FAQ accordion expands/collapses

---

**Built with ❤️ for Yusmad Catering Services**  
**Professional Luxury Catering in Kuala Lumpur, Malaysia**