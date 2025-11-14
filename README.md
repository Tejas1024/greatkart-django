# GreatKart 🛒

A fully-featured e-commerce platform built with Django, offering a seamless online shopping experience. GreatKart provides a robust foundation for building modern online stores with product management, category organization, and user account functionality.

## 📋 Features

- **Product Management**
  - Comprehensive product catalog with detailed product pages
  - Product images, descriptions, pricing, and stock tracking
  - Dynamic URL generation for SEO-friendly links
  - Stock availability management

- **Category System**
  - Hierarchical product categorization
  - Category-based product filtering
  - Dynamic category navigation
  - SEO-optimized category slugs

- **User Account Management**
  - Custom user model with extended fields
  - User registration and authentication
  - Admin panel for user management
  - Role-based permissions (admin, staff, superadmin)

- **Store Features**
  - Browse all products or filter by category
  - Detailed product view pages
  - Product search functionality
  - Responsive design for mobile and desktop

- **Admin Dashboard**
  - Django admin integration
  - Product and category management
  - User administration
  - Inventory tracking

## 🛠️ Tech Stack

- **Backend Framework:** Django 5.2
- **Database:** SQLite (development) - easily configurable for PostgreSQL/MySQL
- **Frontend:** HTML5, CSS3, Bootstrap 4
- **JavaScript:** jQuery 2.0.0
- **Icons:** Font Awesome 5
- **Image Handling:** Pillow
- **Authentication:** Django Built-in Auth System

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)
- Virtual environment (recommended)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd greatkart
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install django==5.2
   pip install pillow
   ```

4. **Apply database migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **Create a superuser**
   ```bash
   python manage.py createsuperuser
   ```
   Follow the prompts to set up your admin account.

6. **Run the development server**
   ```bash
   python manage.py runserver
   ```

7. **Access the application**
   - Frontend: `http://127.0.0.1:8000/`
   - Admin Panel: `http://127.0.0.1:8000/admin/`

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the root directory (optional for production):

```env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
DATABASE_URL=your-database-url
```

### Media Files

Ensure the following directories exist for media uploads:
- `media/photos/products/` - Product images
- `media/photos/categories/` - Category images

### Static Files

Collect static files for production:
```bash
python manage.py collectstatic
```

## 🚀 Usage

### Adding Products

1. Log in to the admin panel at `/admin/`
2. Navigate to **Store > Products**
3. Click **Add Product**
4. Fill in product details:
   - Product name (auto-generates slug)
   - Description
   - Price
   - Stock quantity
   - Category
   - Upload product image
5. Save the product

### Managing Categories

1. Go to **Category > Categories** in admin
2. Add new categories with:
   - Category name
   - Slug (auto-populated)
   - Description
   - Category image (optional)

### Viewing the Store

- Homepage: Displays featured/popular products
- Store page: Browse all products with category filtering
- Product detail page: View individual product information
- Categories are accessible via dropdown menu

## 📁 Project Structure

```
greatkart/
│
├── accounts/              # User account management
│   ├── models.py         # Custom user model
│   ├── admin.py          # User admin configuration
│   └── views.py          # Account views
│
├── category/             # Product category management
│   ├── models.py         # Category model
│   ├── admin.py          # Category admin
│   ├── context_processors.py  # Global category context
│   └── views.py
│
├── store/                # Main store functionality
│   ├── models.py         # Product model
│   ├── views.py          # Store and product views
│   ├── admin.py          # Product admin
│   └── urls.py           # Store URL patterns
│
├── templates/            # HTML templates
│   ├── base.html         # Base template
│   ├── home.html         # Homepage
│   ├── includes/         # Reusable components
│   │   ├── navbar.html
│   │   └── footer.html
│   └── store/
│       ├── store.html    # Product listing
│       └── product_detail.html
│
├── static/               # Static assets
│   ├── css/
│   ├── js/
│   ├── images/
│   └── fonts/
│
├── media/                # User-uploaded files
│   └── photos/
│       ├── products/
│       └── categories/
│
├── greatkart/            # Project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── manage.py             # Django management script
├── .gitignore
└── README.md
```

## 📸 Screenshots

*Coming soon - Add screenshots of:*
- Homepage
- Product listing page
- Product detail page
- Category filtering
- Admin dashboard

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
5. Push to the branch (`git push origin feature/AmazingFeature`)
6. Open a Pull Request

### Coding Standards

- Follow PEP 8 style guide for Python code
- Write meaningful commit messages
- Add comments for complex logic
- Update documentation as needed

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Authors

- Initial work - GreatKart Development Team

## 🙏 Acknowledgments

- Django documentation and community
- Bootstrap for responsive design
- Font Awesome for icons
- All contributors and testers

## 📞 Support

For support, email support@greatkart.com or open an issue in the repository.

## 🔮 Future Enhancements

- [ ] Shopping cart functionality
- [ ] Order management system
- [ ] Payment gateway integration
- [ ] Product reviews and ratings
- [ ] Wishlist feature
- [ ] Email notifications
- [ ] Advanced search and filters
- [ ] Product recommendations
- [ ] Multi-language support
- [ ] API development for mobile apps

---

**Note:** This is a development version. For production deployment, ensure you:
- Change `DEBUG = False` in settings
- Use a production-grade database (PostgreSQL/MySQL)
- Configure proper security settings
- Set up HTTPS
- Use environment variables for sensitive data
- Configure email backend
- Set up proper media and static file serving
