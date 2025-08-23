# Stock Market Analysis Platform

A web application for Indian stock market analysis, investment simulation, and portfolio management built with Flask and vanilla JavaScript.

## Features

- Real-time stock data from Indian markets (NSE/BSE)
- Technical analysis (SMA, EMA, RSI, Bollinger Bands)
- Investment simulation with multiple forecasting models
- Stock rating system
- Portfolio management
- Interactive charts

## Tech Stack

**Backend:** Flask, MySQL, SQLAlchemy  
**Frontend:** HTML/CSS/JavaScript, Bootstrap, Chart.js  
**Data Source:** IndianAPI.in

## Project Structure

```
stock-market-project/
├── backend/
│   ├── app/
│   │   ├── __init__.py          # Flask app factory
│   │   ├── config.py            # Environment-based configuration
│   │   ├── extensions.py        # Database, JWT, caching initialization
│   │   ├── main.py              # Application entry point
│   │   ├── routes/              # API blueprints
│   │   │   ├── __init__.py
│   │   │   ├── stock_routes.py  # Stock data endpoints
│   │   │   ├── user_routes.py   # Authentication endpoints
│   │   │   └── portfolio.py     # Portfolio management
│   │   ├── models/              # SQLAlchemy models
│   │   │   ├── __init__.py
│   │   │   ├── user.py          # User model with auth
│   │   │   └── stock.py         # Stock-related models
│   │   ├── services/            # Business logic layer
│   │   │   ├── __init__.py
│   │   │   ├── stock_service.py # External API integration
│   │   │   ├── analysis.py      # Technical indicators
│   │   │   ├── simulation.py    # Investment projections
│   │   │   └── rating.py        # Stock rating engine
│   │   └── utils/               # Utility functions
│   │       ├── __init__.py
│   │       ├── cache.py         # Caching utilities
│   │       └── logger.py        # Logging configuration
│   ├── tests/                   # Test suites
│   │   ├── test_stocks.py       # Stock functionality tests
│   │   └── test_users.py        # User management tests
│   ├── requirements.txt         # Python dependencies
│   └── wsgi.py                  # Production WSGI entry point
├── frontend/                    # Client-side application
│   ├── index.html               # Main application page
│   ├── styles/
│   │   └── style.css           # Custom styles and themes
│   └── scripts/
│       ├── app.js              # Core application logic
│       └── charts.js           # Chart rendering utilities
├── database/
│   ├── schema.sql              # Database schema definition
│   └── seed_data.sql           # Sample data for testing
├── docker-compose.yml          # Development environment setup
├── Dockerfile                  # Container configuration
├── .env.template              # Environment variables template
├── .gitignore                 # Git ignore patterns
└── README.md                  # Project documentation

```

## Quick Start

1. **Clone and setup**
   ```bash
   git clone <repository-url>
   cd stock-market-project
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   pip install -r backend/requirements.txt
   ```

2. **Configure environment**
   ```bash
   # Create .env file with:
   DATABASE_URL=mysql://user:password@localhost:3306/stock_analysis
   INDIAN_API_KEY=your_api_key
   SECRET_KEY=your_secret_key
   ```

3. **Setup database**
   ```bash
   mysql -u root -p -e "CREATE DATABASE stock_analysis;"
   mysql -u root -p stock_analysis < database/schema.sql
   ```

4. **Run application**
   ```bash
   # Backend
   cd backend
   python main.py
   
   # Frontend (new terminal)
   cd frontend
   python -m http.server 3000
   ```

5. **Access**: Frontend at http://localhost:3000, Backend at http://localhost:5000

## Environment Variables

```env
DATABASE_URL=mysql://username:password@localhost:3306/stock_analysis
INDIAN_API_KEY=your_indianapi_key
SECRET_KEY=your_flask_secret_key
DEBUG=True
```

## API Endpoints

- `GET /api/stock/<symbol>` - Get stock data and analysis
- `POST /api/stock/simulate` - Investment simulation
- `GET /api/rating/<symbol>` - Stock rating
- `GET/POST/PUT/DELETE /api/portfolio` - Portfolio management
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login

## Development

**Run tests:**
```bash
cd backend
pytest tests/ -v
```

**Docker (optional):**
```bash
docker-compose up -d
```

## Deployment

**Production with Gunicorn:**
```bash
cd backend
gunicorn -w 4 -b 0.0.0.0:5000 wsgi:app
```

## Important Disclaimer

⚠️ **This application is for educational purposes only. It does not constitute financial advice. Always consult qualified financial advisors before making investment decisions.**

## License

MIT License

## Support

For issues and questions, please open a GitHub issue.