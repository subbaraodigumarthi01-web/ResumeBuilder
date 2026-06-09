# Resume Builder

A professional resume builder web application built with Django backend and HTML5/CSS3 frontend. Create, customize, and download beautiful resumes.

## Features

✨ **Core Features**
- User registration and authentication
- Create and manage multiple resumes
- Multiple professional resume templates
- Real-time resume preview
- PDF export functionality
- Cloud storage for resumes
- Responsive design (mobile-friendly)

📝 **Resume Sections**
- Personal Information
- Professional Summary
- Work Experience
- Education
- Skills
- Projects
- Certifications

## Tech Stack

- **Backend**: Django 4.2.0, Python 3.x
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Database**: SQLite (development), PostgreSQL (production)
- **PDF Generation**: WeasyPrint
- **Image Processing**: Pillow

## Project Structure

```
ResumeBuilder/
├── manage.py
├── requirements.txt
├── .gitignore
├── .env.example
├── resumebuilder/              # Main project
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   ├── asgi.py
├── users/                      # User management app
│   ├── migrations/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── forms.py
├── resumes/                    # Resume management app
│   ├── migrations/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── forms.py
│   └── utils.py
├── templates/                  # HTML templates
│   ├── base.html
│   ├── home.html
│   ├── dashboard.html
│   ├── editor.html
│   ├── preview.html
│   ├── auth/
│   │   ├── login.html
│   │   ├── register.html
│   │   └── logout.html
│   └── resumes/
│       ├── list.html
│       ├── detail.html
│       └── templates/
├── static/                     # Static files
│   ├── css/
│   │   ├── style.css
│   │   ├── templates.css
│   │   └── editor.css
│   ├── js/
│   │   ├── main.js
│   │   ├── editor.js
│   │   └── api.js
│   └── images/
└── media/                      # User uploaded files
```

## Installation

### Prerequisites
- Python 3.8+
- pip
- virtualenv

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/subbaraodigumarthi01-web/ResumeBuilder.git
   cd ResumeBuilder
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Create .env file**
   ```bash
   cp .env.example .env
   ```

5. **Run migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create superuser**
   ```bash
   python manage.py createsuperuser
   ```

7. **Collect static files**
   ```bash
   python manage.py collectstatic --noinput
   ```

8. **Run development server**
   ```bash
   python manage.py runserver
   ```

Visit `http://localhost:8000` in your browser.

## Usage

### Creating a Resume
1. Sign up or login to your account
2. Click "Create New Resume"
3. Select a template (Classic, Modern, Creative, Minimal)
4. Fill in your information in the editor
5. View real-time preview on the right
6. Save your resume
7. Download as PDF

### Managing Resumes
- View all your resumes in the dashboard
- Edit any resume anytime
- Download as PDF
- Delete resumes you don't need

### Resume Templates

**Classic** - Traditional professional format
**Modern** - Clean, contemporary design
**Creative** - Colorful, artistic style
**Minimal** - Minimalist, elegant design

## API Endpoints

### Authentication
- `POST /api/users/register/` - Register new user
- `POST /api/users/login/` - User login
- `POST /api/users/logout/` - User logout
- `GET /api/users/profile/` - Get user profile

### Resumes
- `GET /api/resumes/` - List all resumes
- `POST /api/resumes/create/` - Create new resume
- `GET /api/resumes/<id>/` - Get resume details
- `PUT /api/resumes/<id>/update/` - Update resume
- `DELETE /api/resumes/<id>/delete/` - Delete resume
- `GET /api/resumes/<id>/export-pdf/` - Download as PDF

### Resume Sections
- `POST /api/resumes/<id>/experience/` - Add experience
- `POST /api/resumes/<id>/education/` - Add education
- `POST /api/resumes/<id>/skill/` - Add skill
- `POST /api/resumes/<id>/project/` - Add project
- `POST /api/resumes/<id>/certification/` - Add certification

## Configuration

Edit `.env` file to configure:
- `DEBUG` - Set to False in production
- `SECRET_KEY` - Django secret key
- `ALLOWED_HOSTS` - Allowed hostnames
- `DATABASE_URL` - Database connection
- `CORS_ALLOWED_ORIGINS` - Allowed origins for CORS

## Development

### Creating Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### Running Tests
```bash
python manage.py test
```

### Accessing Admin Panel
Visit `http://localhost:8000/admin/` with superuser credentials.

## Deployment

### Using Gunicorn
```bash
gunicorn resumebuilder.wsgi:application --bind 0.0.0.0:8000
```

### Using Docker (Optional)
```bash
docker build -t resume-builder .
docker run -p 8000:8000 resume-builder
```

## Security Notes

- Change `SECRET_KEY` in production
- Set `DEBUG=False` in production
- Use environment variables for sensitive data
- Enable HTTPS
- Configure ALLOWED_HOSTS properly
- Use strong database passwords

## Performance Tips

- Enable caching with Redis
- Use CDN for static files
- Compress images
- Minify CSS and JavaScript
- Use database indexing

## Troubleshooting

### Issue: Static files not loading
```bash
python manage.py collectstatic --clear --noinput
```

### Issue: Database errors
```bash
python manage.py migrate --run-syncdb
```

### Issue: Port 8000 already in use
```bash
python manage.py runserver 8001
```

## Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see LICENSE file for details.

## Support

For support, email support@resumebuilder.com or create an issue in the repository.

## Roadmap

- [ ] Multi-language support
- [ ] Advanced styling options
- [ ] AI-powered content suggestions
- [ ] LinkedIn integration
- [ ] Social sharing
- [ ] Cover letter builder
- [ ] Job matching
- [ ] Mobile app
- [ ] Cloud storage integration (Google Drive, Dropbox)
- [ ] Team collaboration features

## Authors

- **Subbarao Digumarthi** - Initial work

## Acknowledgments

- Django documentation
- Bootstrap framework inspiration
- WeasyPrint for PDF generation
