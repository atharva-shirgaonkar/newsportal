# News Portal

A complete news management system built with PHP, MySQL, and Bootstrap. This project provides a full-featured news portal with an admin panel for content management.

## 📋 Table of Contents

- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Database Setup](#database-setup)
- [Configuration](#configuration)
- [Usage](#usage)
- [Admin Panel](#admin-panel)
- [Customization](#customization)
- [Security Features](#security-features)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### Frontend Features
- **Responsive Design**: Mobile-friendly layout using Bootstrap
- **News Display**: Paginated news listing with featured images
- **Category Management**: Browse news by categories and subcategories
- **Search Functionality**: Search news articles by title
- **Comment System**: User comments with admin moderation
- **Contact Form**: Email contact form with validation
- **About/Contact Pages**: Dynamic content management

### Admin Panel Features
- **Dashboard**: Overview with statistics and quick access
- **Content Management**:
  - Add, edit, and delete news posts
  - Category and subcategory management
  - Image upload and management
  - Rich text editor (Summernote)
- **Comment Moderation**: Approve/disapprove user comments
- **User Management**: Admin authentication and password change
- **Page Management**: Edit About and Contact page content
- **Trash Management**: Soft delete with restore functionality

## 🛠 Technology Stack

### Backend
- **PHP**: Server-side scripting
- **MySQL**: Database management
- **Apache/Nginx**: Web server

### Frontend
- **HTML5**: Markup language
- **CSS3**: Styling with Bootstrap framework
- **JavaScript**: Client-side functionality
- **jQuery**: JavaScript library
- **Bootstrap 3.3.7**: Responsive CSS framework

### Admin Panel
- **Custom Admin Theme**: Zircos Dashboard theme
- **Summernote**: Rich text editor
- **Select2**: Enhanced select boxes
- **jQuery Filer**: File upload management
- **Switchery**: Toggle switches

### Build Tools
- **Gulp**: Task automation
- **BrowserSync**: Live reload development

## 📁 Project Structure

```
newsportal/
├── admin/                          # Admin panel files
│   ├── assets/                     # Admin CSS, JS, images
│   ├── includes/                   # Admin includes
│   ├── postimages/                 # Uploaded post images
│   ├── add-category.php           # Add category
│   ├── add-post.php               # Add news post
│   ├── add-subcategory.php        # Add subcategory
│   ├── change-image.php           # Change post image
│   ├── change-password.php        # Change admin password
│   ├── dashboard.php              # Admin dashboard
│   ├── edit-category.php          # Edit category
│   ├── edit-post.php              # Edit news post
│   ├── edit-subcategory.php       # Edit subcategory
│   ├── index.php                  # Admin login
│   ├── logout.php                 # Admin logout
│   ├── manage-categories.php      # Manage categories
│   ├── manage-comments.php        # Manage approved comments
│   ├── manage-posts.php           # Manage news posts
│   ├── manage-subcategories.php   # Manage subcategories
│   ├── trash-posts.php            # Manage deleted posts
│   ├── unapprove-comment.php      # Manage pending comments
│   └── aboutus.php, contactus.php # Page management
├── css/                           # Frontend stylesheets
│   └── modern-business.css        # Custom styles
├── images/                        # Static images
│   ├── logo.png                   # Site logo
│   └── usericon.png               # User avatar
├── includes/                      # Frontend includes
│   ├── config.php                 # Database configuration
│   ├── header.php                 # Site header
│   ├── footer.php                 # Site footer
│   └── sidebar.php                # Sidebar widgets
├── js/                           # JavaScript files
│   ├── contact_me.js             # Contact form validation
│   └── jqBootstrapValidation.js  # Bootstrap validation
├── mail/                         # Email handling
│   └── contact_me.php            # Contact form processing
├── plugins/                      # Third-party plugins
│   ├── bootstrap/                # Bootstrap framework
│   ├── jquery/                   # jQuery library
│   ├── summernote/               # Rich text editor
│   ├── select2/                  # Enhanced selects
│   └── [other plugins...]        # Various UI components
├── vendor/                       # Vendor libraries
│   ├── bootstrap/                # Bootstrap files
│   └── jquery/                   # jQuery files
├── about-us.php                  # About page
├── category.php                  # Category listing
├── contact-us.php                # Contact page
├── gulpfile.js                   # Gulp build configuration
├── index.php                     # Homepage
├── news-details.php              # Individual news view
└── search.php                    # Search results
```

## 🚀 Installation

### Prerequisites
- PHP 7.0 or higher
- MySQL 5.6 or higher
- Apache/Nginx web server
- Node.js and npm (for development)

### Step 1: Clone or Download
```bash
# Clone the repository
git clone [repository-url]
cd newsportal

# Or download and extract the ZIP file
```

### Step 2: Web Server Setup
1. Place the project files in your web server's document root
2. Ensure the web server has read/write permissions for the `admin/postimages/` directory
3. Configure your web server to serve PHP files

### Step 3: Install Dependencies (Development)
```bash
# Install Node.js dependencies
npm install

# Install vendor libraries
gulp vendor

# Start development server
gulp dev
```

## 🗄 Database Setup

### Step 1: Create Database
```sql
CREATE DATABASE newsportal;
USE newsportal;
```

### Step 2: Import Database Schema
The project requires the following tables (you'll need to create the SQL schema):

**Main Tables:**
- `tbladmin` - Admin user accounts
- `tblcategory` - News categories
- `tblsubcategory` - News subcategories
- `tblposts` - News articles
- `tblcomments` - User comments
- `tblpages` - Static page content

### Step 3: Default Admin Account
Create an admin user with hashed password:
```sql
INSERT INTO tbladmin (AdminUserName, AdminEmailId, AdminPassword, AdminRegdate) 
VALUES ('admin', 'admin@example.com', '$2y$12$hashedpassword', NOW());
```

## ⚙ Configuration

### Database Configuration
Edit `includes/config.php`:
```php
<?php
define('DB_SERVER','localhost');
define('DB_USER','your_username');
define('DB_PASS','your_password');
define('DB_NAME','newsportal');
```

### Email Configuration
Edit `mail/contact_me.php`:
```php
$to = 'your-email@domain.com'; // Your email address
$headers = "From: noreply@yourdomain.com\n";
```

### Admin Panel Access
- URL: `http://yoursite.com/admin/`
- Default credentials: Check your database or contact administrator

## 📖 Usage

### Frontend Usage

#### Viewing News
1. **Homepage**: Visit the main site to see latest news
2. **Categories**: Click on category links to filter news
3. **Search**: Use the search box to find specific articles
4. **Individual Articles**: Click "Read More" to view full articles

#### User Interaction
1. **Comments**: Leave comments on news articles (requires admin approval)
2. **Contact**: Use the contact form to send messages
3. **Navigation**: Use the top navigation menu

### Admin Panel Usage

#### Dashboard
- View statistics: Categories, Subcategories, Live News, Trash
- Quick access to all management functions

#### Content Management
1. **Add News**:
   - Go to Posts → Add Posts
   - Fill in title, category, subcategory, content
   - Upload featured image
   - Submit

2. **Manage Categories**:
   - Go to Category → Add Category
   - Create categories and subcategories
   - Edit or delete existing categories

3. **Manage Posts**:
   - View all published posts
   - Edit post content and images
   - Move posts to trash

#### Comment Moderation
1. **Pending Comments**: Review and approve/disapprove
2. **Approved Comments**: Manage published comments
3. **Delete Comments**: Remove inappropriate content

#### Page Management
- Edit About Us page content
- Edit Contact Us page content
- Use rich text editor for formatting

## 🔧 Customization

### Styling
- **Frontend**: Edit `css/modern-business.css`
- **Admin Panel**: Modify `admin/assets/css/` files
- **Bootstrap**: Customize Bootstrap variables

### Functionality
- **Contact Form**: Modify `mail/contact_me.php`
- **Validation**: Edit `js/contact_me.js`
- **Admin Features**: Extend admin panel files

### Content
- **Static Pages**: Edit through admin panel
- **Categories**: Manage through admin interface
- **Images**: Upload through admin panel

## 🔒 Security Features

### Frontend Security
- **CSRF Protection**: Token-based protection for forms
- **Input Validation**: Server-side validation
- **XSS Prevention**: HTML entity encoding
- **SQL Injection Prevention**: Prepared statements

### Admin Security
- **Password Hashing**: Bcrypt password hashing
- **Session Management**: Secure session handling
- **Access Control**: Admin-only areas protected
- **File Upload Security**: Image type validation

### Database Security
- **Connection Security**: Secure database connections
- **Query Protection**: Parameterized queries
- **Error Handling**: Graceful error management

## 🤝 Contributing

### Development Setup
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Code Standards
- Follow PHP PSR standards
- Use meaningful variable names
- Add comments for complex logic
- Test all functionality

### Reporting Issues
- Use GitHub issues
- Provide detailed bug reports
- Include steps to reproduce
- Specify environment details


### Usage Terms
- Free for personal and commercial use
- Attribution required
- No warranty provided
- Use at your own risk


### Getting Help
1. Check the documentation
2. Review existing issues
3. Contact the developer
4. Join the community

---

**Note**: This is a complete news portal solution with both frontend and admin functionality. Make sure to configure your database and email settings before deployment. 
