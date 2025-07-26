# 🌟 Professional CV Creator

A modern web application that creates professional, ATS-friendly CVs in Microsoft Word format. Built with Flask and designed for easy deployment on Render.

## ✨ Features

- **Professional Formatting**: Industry-standard layout with custom typography
- **ATS-Friendly**: Optimized for Applicant Tracking Systems
- **Responsive Design**: Works perfectly on desktop and mobile devices
- **Instant Download**: Generate Word documents (.docx) instantly
- **Multiple Sections**: Personal info, experience, education, skills, projects
- **Dynamic Forms**: Add/remove sections as needed
- **Professional Templates**: Based on Fortune 500 hiring standards

## 🚀 Quick Start

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/pato7y/cv-creator.git
   cd cv-creator
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

4. **Run the application**
   ```bash
   python app.py
   ```

5. **Open browser**
   Navigate to `http://localhost:5000`

### Docker Development

1. **Build and run with Docker Compose**
   ```bash
   docker-compose up --build
   ```

2. **Access the application**
   Open `http://localhost:5000`

## 🐳 Docker Deployment

### Build Docker Image
```bash
docker build -t cv-creator .
```

### Run Docker Container
```bash
docker run -p 5000:5000 cv-creator
```

## 🌐 Deploy to Render

### Method 1: GitHub Integration (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

2. **Create Render Service**
   - Go to [Render Dashboard](https://dashboard.render.com)
   - Click "New +" → "Web Service"
   - Connect your GitHub repository
   - Configure settings:
     - **Name**: `cv-creator`
     - **Environment**: `Docker`
     - **Plan**: Free (or paid for better performance)
     - **Auto-Deploy**: Yes

3. **Environment Variables** (Optional)
   ```
   FLASK_ENV=production
   PORT=5000
   ```

### Method 2: Direct Docker Deploy

1. **Create render.yaml**
   ```yaml
   services:
     - type: web
       name: cv-creator
       env: docker
       dockerfilePath: ./Dockerfile
       plan: free
       healthCheckPath: /health
       envVars:
         - key: PORT
           value: 5000
   ```

2. **Deploy via Render Dashboard**
   - Upload your code as ZIP
   - Select Docker environment
   - Deploy

## 📁 Project Structure

```
cv-creator/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── Dockerfile            # Docker configuration
├── docker-compose.yml    # Docker Compose setup
├── render.yaml          # Render deployment config
├── templates/
│   └── index.html       # Main web interface
├── static/              # Static files (if needed)
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## 🛠️ Technology Stack

- **Backend**: Flask (Python)
- **Document Generation**: python-docx
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5
- **Containerization**: Docker
- **Deployment**: Render
- **Version Control**: Git

## 📋 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Main web interface |
| `/create-cv` | POST | Generate CV document |
| `/health` | GET | Health check endpoint |

## 🎨 Customization

### Styling
- Modify CSS variables in `templates/index.html`
- Customize colors, fonts, and layout
- Add new sections or form fields

### Document Format
- Edit `WebCVCreator` class in `app.py`
- Modify document styles and formatting
- Add new sections or content types

## 🔧 Configuration

### Environment Variables
```bash
FLASK_ENV=production        # Flask environment
PORT=5000                  # Application port
FLASK_DEBUG=False          # Debug mode (production)
```

### Docker Configuration
- **Base Image**: `python:3.11-slim`
- **Port**: 5000
- **Health Check**: `/health` endpoint
- **Auto-restart**: Unless stopped

## 📱 Usage Guide

1. **Fill Personal Information**
   - Name, contact details, professional title
   - LinkedIn, GitHub, portfolio links
   - Professional summary

2. **Add Work Experience**
   - Job titles, companies, dates
   - Responsibilities and achievements
   - Use action verbs and quantify results

3. **Include Education**
   - Degrees, institutions, dates
   - GPA (if 3.5+), honors, relevant coursework

4. **List Skills**
   - Categorize by type (Technical, Soft Skills, etc.)
   - Include proficiency levels

5. **Add Projects** (Optional)
   - Personal, professional, or academic projects
   - Technologies used, links, achievements

6. **Download CV**
   - Click "Create & Download CV"
   - Receive professionally formatted Word document

## 🚀 Performance Optimization

### For Production

1. **Use Gunicorn**
   ```bash
   pip install gunicorn
   gunicorn --bind 0.0.0.0:5000 app:app
   ```

2. **Enable Caching**
   - Add Redis for session storage
   - Implement template caching

3. **Optimize Docker Image**
   - Use multi-stage builds
   - Remove unnecessary packages

## 🐛 Troubleshooting

### Common Issues

1. **Port Already in Use**
   ```bash
   # Kill process on port 5000
   lsof -ti:5000 | xargs kill -9
   ```

2. **Docker Build Fails**
   ```bash
   # Clear Docker cache
   docker system prune -a
   ```

3. **Requirements Installation Fails**
   ```bash
   # Upgrade pip
   pip install --upgrade pip
   ```

### Logs and Debugging

```bash
# View Docker logs
docker logs container_name

# Check application status
curl http://localhost:5000/health
```

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request



## 🙏 Acknowledgments

- Bootstrap for responsive UI components
- python-docx for Word document generation
- Font Awesome for icons
- Render for hosting platform

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/pato7y/cv-creator/issues)
- **Documentation**: This README


## 🎯 Roadmap

- [ ] PDF export functionality
- [ ] Multiple CV templates
- [ ] User accounts and saved CVs
- [ ] Integration with job boards
- [ ] Mobile app version
- [ ] AI-powered content suggestions

---

**Happy CV Creating! 🎉**

Made with ❤️ for job seekers worldwide.
