# Academic Performance Pattern Detector - AI-Powered Learning Coach

A production-ready Flask application that tracks study habits, wellness metrics, and academic performance using AI to provide personalized learning insights and optimization recommendations.

## Features

- 🧠 **AI-Powered Insights**: Personalized study analysis using Google's Gemini AI
- 📊 **Visual Analytics**: Interactive dashboards with Chart.js visualizations
- 📚 **Study Session Tracking**: Comprehensive logging of study habits and focus levels
- 💪 **Wellness Integration**: Sleep, stress, and mood tracking with performance correlation
- 🎯 **Pattern Recognition**: Automated detection of learning patterns and optimization opportunities
- 🎨 **Modern Dark UI**: Beautiful glassmorphism design with neon accents
- 📱 **Fully Responsive**: Optimized for desktop and mobile devices
- ⚡ **Real-time Processing**: Instant data analysis and pattern detection

## 📸 Screenshots

### 1. 🏠 Landing Page
![Landing Page](screenshots/homepage.png)
*Beautiful animated landing page with AI analysis preview*

---

### 2. 📊 Dashboard Overview
![Dashboard Overview](screenshots/dashboard.png)
*Comprehensive dashboard with study statistics and quick actions*

---

### 3. 📈 Study Session Logging
![Study Session Form](screenshots/log-study.png)
*Detailed study session tracking with focus ratings and methods*

---

### 4. 🧠 AI-Powered Insights
![AI Insights](screenshots/ai-insights.png)
*Personalized recommendations and pattern analysis from Gemini AI*

---

### 5. 🔍 Pattern Analysis
![Pattern Analysis](screenshots/patterns.png)
*Automated pattern detection and correlation analysis*

---

### 6. 💪 Wellness Tracking
![Wellness Tracking](screenshots/wellness.png)
*Comprehensive wellness monitoring with academic performance correlation*

## Prerequisites

- Python 3.8 or higher
- Google Gemini API key
- Modern web browser

## Installation

1. **Clone or download this repository**
   ```bash
   git clone <repository-url>
   cd academic-pattern-detector
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv .venv
   
   # On Windows
   .venv\Scripts\activate
   
   # On macOS/Linux
   source .venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   
   Create a `.env` file in the project root:
   ```bash
   # Create .env file
   echo "GEMINI_API_KEY=your_gemini_api_key_here" > .env
   echo "FLASK_SECRET_KEY=your_secret_key_here" >> .env
   ```

   **Getting a Gemini API Key:**
   - Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Sign in with your Google account
   - Create a new API key
   - Copy the key to your `.env` file

## Usage

1. **Start the application**
   ```bash
   python app.py
   ```

2. **Open your browser**
   Navigate to http://localhost:5000

3. **Start tracking your academic journey**
   - Log study sessions with detailed metrics
   - Record academic performance and grades
   - Track wellness factors (sleep, stress, mood)
   - View AI-powered insights and recommendations

4. **Explore your data**
   - Interactive dashboard with charts
   - Pattern analysis and correlations
   - Personalized optimization tips
   - Progress tracking over time

## Core Features

### 📚 Study Session Tracking
- **Subject Management**: Track multiple subjects
- **Time Tracking**: Start/end times with duration calculation
- **Study Methods**: Various learning techniques (reading, practice, etc.)
- **Focus Rating**: 1-5 scale for concentration levels
- **Difficulty Assessment**: Track content complexity
- **Notes**: Additional context and observations

### 📈 Performance Recording
- **Assessment Types**: Quizzes, exams, assignments, projects
- **Score Tracking**: Numerical grades with percentage calculation
- **Subject Performance**: Track progress across different subjects
- **Topic Coverage**: Document what was assessed
- **Trend Analysis**: Visual progress over time

### 💪 Wellness Monitoring
- **Sleep Tracking**: Hours of sleep and quality impact
- **Stress Levels**: 1-5 scale stress assessment
- **Mood Rating**: Daily mood tracking
- **Exercise**: Physical activity minutes
- **Caffeine Intake**: Consumption tracking
- **Correlation Analysis**: Wellness impact on academic performance

### 🧠 AI-Powered Insights
- **Pattern Recognition**: Identify optimal study conditions
- **Performance Correlations**: Link wellness to academic success
- **Personalized Recommendations**: Tailored improvement strategies
- **Strength Analysis**: Highlight what's working well
- **Optimization Opportunities**: Specific actionable advice

## Database Schema

### Study Sessions Table
```sql
- id: Primary key
- subject: Study subject
- duration: Session length in minutes
- start_time, end_time: Time tracking
- study_method: Learning technique used
- difficulty_level: Content complexity (1-5)
- focus_rating: Concentration level (1-5)
- notes: Additional observations
- created_at: Timestamp
```

### Performance Records Table
```sql
- id: Primary key
- subject: Academic subject
- assessment_type: Type of evaluation
- score, max_score: Grade tracking
- date: Assessment date
- topics_covered: Content areas
- created_at: Timestamp
```

### Wellness Tracking Table
```sql
- id: Primary key
- date: Tracking date
- sleep_hours: Sleep duration
- stress_level: Stress rating (1-5)
- mood_rating: Mood assessment (1-5)
- exercise_minutes: Physical activity
- caffeine_intake: Consumption amount
- notes: Additional context
- created_at: Timestamp
```

## Project Structure

```
academic-pattern-detector/
├── app.py                      # Main Flask application (489 lines)
├── requirements.txt            # Python dependencies
├── .env                       # Environment variables (API keys)
├── .gitignore                 # Git ignore rules
├── README.md                  # This file
├── instance/
│   └── database.db           # SQLite database
├── templates/                # Jinja2 templates
│   ├── base.html            # Landing page template
│   ├── dashboard.html       # Main dashboard UI
│   ├── ai_insights.html     # AI analysis display
│   ├── patterns.html        # Pattern analysis view
│   ├── log_study.html       # Study session logging form
│   ├── log_performance.html # Performance recording form
│   └── log_wellness.html    # Wellness tracking form
├── static/                   # Static assets
│   ├── css/                 # Custom stylesheets
│   ├── js/                  # JavaScript files
│   └── images/              # Image assets
└── .venv/                    # Python virtual environment
```

## Configuration

### Environment Variables

- `GEMINI_API_KEY`: Required for AI-powered insights
- `FLASK_SECRET_KEY`: Session security (optional, has fallback)

### Application Settings

Key configurations in `app.py`:
- Database path: `instance/database.db`
- AI model: `gemini-1.5-flash-latest`
- Debug mode: Enabled by default
- Secret key management with environment fallback

## AI Integration

### Google Gemini AI
- **Model**: `gemini-1.5-flash-latest`
- **Purpose**: Comprehensive study pattern analysis
- **Input**: Aggregated study, performance, and wellness data
- **Output**: Structured insights with actionable recommendations
- **Privacy**: No individual sensitive data shared

### AI Analysis Features
- **Pattern Detection**: Identify optimal study conditions
- **Correlation Analysis**: Link wellness factors to performance
- **Personalized Advice**: Tailored improvement strategies
- **Motivation**: Encouraging, data-driven feedback
- **Actionable Tips**: Specific next steps for optimization

## API Endpoints

### Data API
- `GET /api/study-data`: JSON data for charts and visualizations
- Returns subject-wise study hours and daily trends

### CRUD Operations
- `POST /log-study`: Create new study session
- `POST /log-performance`: Record academic performance
- `POST /log-wellness`: Track wellness metrics
- `POST /delete-study-session/<id>`: Remove study session
- `POST /delete-performance-record/<id>`: Remove performance record
- `POST /delete-wellness-entry/<id>`: Remove wellness entry

## Troubleshooting

### Common Issues

1. **"GEMINI_API_KEY not found"**
   ```bash
   # Verify your .env file contains:
   GEMINI_API_KEY=your_actual_api_key
   ```

2. **Database not initializing**
   ```bash
   # Delete the instance folder and restart
   rm -rf instance/
   python app.py
   ```

3. **Charts not loading**
   - Check browser console for JavaScript errors
   - Ensure internet connection for CDN resources
   - Verify `/api/study-data` endpoint returns valid JSON

4. **AI insights not working**
   - Verify Gemini API key is correct
   - Check for API quota limits
   - Ensure sufficient data (5+ study sessions recommended)

### Performance Tips

- Log at least 5-10 study sessions for meaningful AI insights
- Consistent wellness tracking improves correlation analysis
- Regular performance recording enhances trend analysis
- Use honest focus ratings for accurate pattern detection

## Security Notes

- Never commit API keys to version control
- Use environment variables for sensitive configuration
- Database is local SQLite (not accessible externally)
- Session data is secured with Flask's session management
- Consider HTTPS for production deployment

## Development

### Adding New Features

1. **New study methods**: Edit the form options in `log_study.html`
2. **Additional wellness metrics**: Extend the wellness tracking schema
3. **Custom visualizations**: Modify Chart.js implementations
4. **Enhanced AI prompts**: Customize the analysis prompt in `get_ai_insights()`

### Database Management

```python
# Initialize fresh database
python -c "from app import init_db; init_db()"

# View database contents (requires SQLite browser or command line)
sqlite3 instance/database.db ".tables"
```

## Deployment

For production deployment:

1. Set environment variables properly
2. Use a production WSGI server (Gunicorn, uWSGI)
3. Configure reverse proxy (Nginx, Apache)
4. Set up SSL/TLS certificates
5. Implement proper logging and monitoring
6. Consider PostgreSQL for larger datasets

Example Gunicorn deployment:
```bash
pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:8000 app:app
```

## Sample Data

To test the application with sample data:

1. Start the application
2. Log a few study sessions with different subjects
3. Record some performance data
4. Track wellness metrics for several days
5. Visit AI Insights to see personalized analysis

## License

This project is provided as-is for educational and personal use.

## Support

For issues or questions:
1. Check the troubleshooting section above
2. Ensure all dependencies are installed correctly
3. Verify your Gemini API key is valid
4. Test with sample data first
5. Check browser console for JavaScript errors

## Future Enhancements

- **Goal Setting**: Academic and personal goals with progress tracking
- **Study Groups**: Collaborative features and shared insights
- **Calendar Integration**: Schedule optimization and time management
- **Mobile App**: Native mobile application
- **Advanced Analytics**: Machine learning predictions and trends
- **Export Features**: PDF reports and data export
- **Notification System**: Reminders and achievement alerts

## Acknowledgments

- **Google** for the Gemini AI API
- **Flask** for the excellent web framework
- **Chart.js** for beautiful data visualizations
- **Tailwind CSS** for rapid UI development
- **Font Awesome** for comprehensive icon library
- **SQLite** for reliable data storage

---

Built with ❤️ using AI and modern web technologies to help students optimize their learning journey.

## Contributing

We welcome contributions! Please feel free to submit pull requests or open issues for bugs and feature requests.

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## Changelog

### v1.0.0 (Current)
- Initial release with core functionality
- AI-powered insights integration
- Comprehensive tracking features
- Modern responsive UI
- Pattern analysis capabilities
