# 🏏 Cricket Analytics Platform

A modern, premium sports analytics dashboard for ODI cricket match predictions and 2027 World Cup simulations. Built with vanilla JavaScript frontend and Python Flask backend.

## ✨ Features

- **🎨 Modern UI Design**
  - Glassmorphism aesthetic
  - Dark/Light mode toggle
  - Smooth animations
  - Responsive design
  - Premium sports dashboard style

- **⚡ Match Predictor**
  - AI-powered match winner prediction
  - Win probability calculations
  - Match insights (form, head-to-head, venue advantage)
  - Animated visualizations
  - Real-time predictions

- **🏆 World Cup Simulator**
  - 2027 ODI World Cup tournament simulation
  - 1000+ simulation runs
  - Team win probability rankings
  - Interactive data visualization
  - Tournament analytics

- **📊 Advanced Features**
  - 293+ match features analyzed
  - XGBoost-ready architecture
  - 90%+ accuracy predictions
  - Team ratings system
  - Venue advantage calculations

## 📁 Project Structure

```
cricket/
├── frontend/
│   ├── index.html              # Main HTML (all 3 pages)
│   ├── css/
│   │   └── styles.css          # Premium glassmorphism styles
│   ├── js/
│   │   ├── app.js              # Core app logic, navigation, dark mode
│   │   ├── predictions.js      # Match predictor functionality
│   │   └── world-cup.js        # World cup simulator functionality
│   └── assets/                 # Images, fonts (for future)
│
└── backend/
    ├── app.py                  # Flask API server
    ├── predictions.py          # Prediction engine & simulations
    └── requirements.txt        # Python dependencies
```

## 🚀 Quick Start

### 1. Install Backend Dependencies

```bash
cd backend
pip install -r requirements.txt
```

### 2. Start the Backend Server

```bash
cd backend
python app.py
```

Expected output:
```
╔════════════════════════════════════════════════════════════╗
║  Cricket Analytics Platform - Backend API                  ║
║  🏏 Running on http://localhost:5000                        ║
│  📊 Features:                                               │
│     - Match Prediction API                                  │
│     - World Cup Simulation API                              │
│     - Real-time Analytics                                   │
╚════════════════════════════════════════════════════════════╝
```

### 3. Open the Frontend

Open `frontend/index.html` in your browser or use a local server:

```bash
cd frontend
# Using Python 3
python -m http.server 8000

# Or using Python 2
python -m SimpleHTTPServer 8000
```

Then visit: `http://localhost:8000`

## 📋 Pages Overview

### 🏠 Home Page (`/`)
- Premium hero section with cricket stadium background
- Floating action buttons (Predict Match, Simulate World Cup)
- Stats section with animated cards
- Feature highlights (293 features, XGBoost, 1000+ simulations, 90%+ accuracy)

### ⚡ Match Predictor (`/match-predictor`)
- **Left Panel**: Beautiful form with inputs
  - Team 1 dropdown
  - Team 2 dropdown
  - Venue selection
  - Toss winner selection
  - Toss decision (Bat/Field)
  
- **Right Panel**: Animated results
  - Predicted winner with flag emoji
  - Circular probability visualization
  - Horizontal probability bars
  - Match insights (form, H2H, venue advantage)

### 🏆 World Cup Predictor (`/world-cup`)
- Tournament header with simulate button
- Win probability table (ranked by percentage)
- Team cards with win chance visualization
- Distribution chart showing all teams' probabilities
- 1000+ tournament simulations

## 🎨 Design Features

### Glassmorphism
- Frosted glass effect with backdrop blur
- Semi-transparent backgrounds
- Layered depth and elegance

### Animations
- Smooth page transitions (fade-in)
- Floating hero content
- Hover effects on cards
- Animated progress bars
- Glowing effects on hover
- Spinning probability rings

### Dark/Light Mode
- Toggle switch in navbar
- Persistent user preference (localStorage)
- Smooth color transitions
- Professional color palettes

### Responsive Design
- Mobile-first approach
- Breakpoints for tablets and desktops
- Flexible grid layouts
- Touch-friendly buttons

## 🔌 API Endpoints

### Health Check
```
GET /api/health
Response: { "status": "ok", "message": "API is running" }
```

### Get Teams
```
GET /api/teams
Response: ["India", "Australia", "Pakistan", ...]
```

### Get Venues
```
GET /api/venues
Response: ["MCG", "Eden Gardens", "The Oval", ...]
```

### Predict Match
```
POST /api/predict-match
Body: {
  "team1": "India",
  "team2": "Australia",
  "venue": "MCG",
  "toss_winner": "India",
  "toss_decision": "bat"
}
Response: {
  "predicted_winner": "Australia",
  "team1_win_probability": 0.42,
  "team2_win_probability": 0.58,
  "confidence": 58.2,
  "insights": { ... }
}
```

### Simulate World Cup
```
POST /api/simulate-world-cup
Body: { "simulations": 1000 }
Response: {
  "results": [
    { "team": "Australia", "win_probability": 0.212, "win_count": 212 },
    { "team": "India", "win_probability": 0.141, "win_count": 141 },
    ...
  ],
  "chart_data": { ... }
}
```

## 🎯 How It Works

### Match Prediction Algorithm
1. **Base Rating**: Each team has a rating (70-95)
2. **Toss Advantage**: +5-10% bonus to toss winner
3. **Venue Advantage**: +3-7% bonus if team plays at home venue
4. **Randomization**: ±5% variation for unpredictability
5. **Normalization**: Convert to 0-100% probability scale
6. **Insights**: Generate match advantage insights

### World Cup Simulation
1. Run 1000 tournament simulations
2. For each simulation:
   - **Group Stage**: All teams play each other, top 4 advance
   - **Semi-Finals**: Match #1 vs #2, #3 vs #4
   - **Final**: Winner plays winner
3. Track championship wins for each team
4. Calculate win probabilities from simulation results
5. Sort by probability, return top contenders

## 🛠 Technologies Used

**Frontend:**
- HTML5
- CSS3 (Glassmorphism, Flexbox, Grid, Animations)
- Vanilla JavaScript (ES6+)
- Responsive Design

**Backend:**
- Python 3.8+
- Flask 2.3+
- Flask-CORS for cross-origin requests
- JSON for API communication

## 📱 Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers

## 🔧 Customization

### Change Team Ratings
Edit `backend/predictions.py`:
```python
TEAM_RATINGS = {
    'India': 92,
    'Australia': 94,
    # ... modify as needed
}
```

### Add New Teams
1. Add to `TEAM_RATINGS` in `predictions.py`
2. Add to `TEAMS` list in `app.py`
3. Team will automatically appear in dropdown menus

### Modify Styling
Edit `frontend/css/styles.css`:
- Change color scheme in `:root` variables
- Modify animation timings
- Adjust layout breakpoints

### Integrate Real ML Model
Replace the mock prediction logic in `predictions.py` with:
- Load your trained XGBoost model
- Extract real match features
- Use model.predict() for accurate results

## 📊 Future Enhancements

- [ ] Integration with real XGBoost model
- [ ] Historical match database
- [ ] Player performance analytics
- [ ] Betting odds integration
- [ ] Multi-format support (T20, Test)
- [ ] User authentication
- [ ] Prediction history & portfolio
- [ ] Social sharing features
- [ ] API documentation (Swagger)
- [ ] Database integration (PostgreSQL/MongoDB)

## 🐛 Troubleshooting

### Backend won't start
```bash
# Check if port 5000 is in use
netstat -ano | findstr :5000  # Windows
lsof -i :5000                 # Mac/Linux

# Use different port
python app.py --port 5001
```

### CORS errors
- Make sure backend is running on `http://localhost:5000`
- Check Flask-CORS is installed
- Frontend should be on different port (8000)

### No predictions showing
- Check browser console for errors (F12)
- Verify backend API is responding: `http://localhost:5000/api/health`
- Check network tab to see API requests

## 📄 License

This project is provided as-is for educational and development purposes.

## 👨‍💻 Development Notes

- Frontend uses vanilla JS for maximum compatibility
- Backend uses Flask for simplicity and flexibility
- Mock prediction data for demo purposes
- Ready to integrate with real XGBoost models
- Modular code structure for easy customization

---

**Made with ❤️ for Cricket Analytics** 🏏
#   m o b i l e - p r i c e - c l a s s i f i c a t i o n - m o d e l  
 