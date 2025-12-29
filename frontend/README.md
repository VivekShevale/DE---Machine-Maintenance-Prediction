# Machine Maintenance Prediction System - Frontend

A comprehensive React + Vite frontend application for AI-powered predictive maintenance, featuring real-time sensor monitoring, failure predictions, and maintenance analytics.

## 📋 Table of Contents

- Features
- Tech Stack
- Getting Started
- Project Structure
- Key Pages
- Components
- Installation
- Development
- Build & Deployment
- Configuration

## ✨ Features

### Dashboard
- Real-time machine health monitoring
- Overall Equipment Effectiveness (OEE) metrics
- Critical alerts and notifications
- Machine health status table with risk assessment
- Temperature and vibration trend charts
- Failure type distribution analysis

### Sensor Data Monitoring
- Live sensor data streaming (5-second updates)
- Multi-sensor visualization (Temperature, Vibration, Pressure, RPM, Voltage, Current)
- Customizable time ranges (1h, 6h, 24h, 7d, 30d)
- Interactive charts with real-time data
- CSV export functionality
- Custom chart creation and management
- Detailed sensor information and thresholds

### Predictive Analytics
- Multiple AI model support (Random Forest, XGBoost, LSTM)
- Failure probability predictions with confidence scores
- Time-to-failure (TTF) estimations
- Risk factor analysis using radar charts
- Model performance metrics and comparison
- Prediction accuracy tracking over time
- Report generation and export

### Maintenance Management
- Maintenance history tracking
- Preventive, corrective, and predictive maintenance types
- Technician assignment and tracking
- Cost analysis and ROI metrics
- MTBF (Mean Time Between Failures) and MTTR (Mean Time To Repair) KPIs
- Parts replacement documentation

### Alerts & Notifications
- Real-time alert system with severity levels
- Alert acknowledgment and tracking
- Recommended actions for each alert
- Email and push notification settings
- Alert filtering and search capabilities

### System Settings
- Sensor threshold configuration
- Notification preferences
- API key management
- ML model status monitoring
- Database and system information

### Reports & Analytics
- Multiple report types (Summary, Analysis, Financial, Technical)
- Date range filtering
- Charts and visualizations
- Export to PDF/CSV
- Sharing capabilities
- Performance metrics and trends

## 🛠 Tech Stack

- **Framework**: React 19.2.0
- **Build Tool**: Vite 5.1+
- **Styling**: Tailwind CSS 4.1+
- **Routing**: React Router DOM 7.11+
- **Charts**: Recharts 3.6.0
- **Icons**: Lucide React 0.562.0
- **Language**: JavaScript (ES6+)
- **Linting**: ESLint 9.39+

## 🚀 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn package manager

### Installation

1. **Clone the repository**
```bash
git clone <repository-url>
cd frontend
```

2. **Install dependencies**
```bash
npm install
```

3. **Start development server**
```bash
npm run dev
```

The application will be available at `http://localhost:5173`

## 📁 Project Structure

```
frontend/
├── src/
│   ├── components/
│   │   ├── Navbar.jsx          # Top navigation bar
│   │   └── Sidebar.jsx         # Side navigation menu
│   ├── pages/
│   │   ├── Dashboard.jsx       # Main dashboard
│   │   ├── SensorData.jsx      # Real-time sensor monitoring
│   │   ├── Predictions.jsx     # AI predictions and analytics
│   │   ├── Alerts.jsx          # Alert management
│   │   ├── MaintenanceHistory.jsx # Maintenance records
│   │   ├── Reports.jsx         # Reports and analytics
│   │   ├── Settings.jsx        # System settings
│   │   ├── MachineDetails.jsx  # Individual machine details
│   │   └── Login.jsx           # Authentication
│   ├── App.jsx                 # Main app component
│   ├── App.css                 # Global styles
│   ├── index.css               # Tailwind configuration
│   └── main.jsx                # Entry point
├── public/
│   └── vite.svg
├── package.json
├── vite.config.js
├── eslint.config.js
└── index.html
```

## 📄 Key Pages

### Dashboard
Main overview page showing:
- System-wide health metrics
- Machine status table with risk levels
- Upcoming maintenance schedule
- Temperature and vibration trends
- Failure distribution pie chart
- Quick action buttons

### Sensor Data
Real-time monitoring interface:
- Live sensor readings and status indicators
- Multi-sensor trend charts
- Customizable time range selection
- Machine-specific data filtering
- Custom chart creation
- Data export functionality

### Predictions
AI-powered failure predictions:
- Multiple model selection
- Active predictions list
- Prediction confidence scores
- Time-to-failure estimations
- Risk factor analysis
- Model performance metrics
- Report generation

### Alerts
Alert management system:
- Real-time alert display
- Severity-based filtering
- Alert acknowledgment
- Recommended actions
- Alert history

### Maintenance History
Historical maintenance records:
- Maintenance events timeline
- Cost analysis
- Technician tracking
- Parts management
- Performance KPIs (MTBF, MTTR)

### Reports
Analytics and reporting:
- Multiple report types
- Chart visualizations
- Date range filtering
- Export capabilities
- Performance metrics

### Settings
System configuration:
- Sensor threshold management
- Notification preferences
- API key management
- System monitoring status

### Machine Details
Individual machine analysis:
- Detailed machine specifications
- Performance charts
- Maintenance scheduling
- Edit machine information
- Export machine data

## 🧩 Components

### Navbar
- Branding and logo
- Search functionality
- User profile menu
- Alert notifications
- Quick navigation

### Sidebar
- Main navigation menu
- Machine list with status indicators
- Quick action buttons
- System status display

## 📦 Dependencies

```json
{
  "react": "^19.2.0",
  "react-dom": "^19.2.0",
  "react-router-dom": "^7.11.0",
  "recharts": "^3.6.0",
  "lucide-react": "^0.562.0",
  "tailwindcss": "^4.1.18",
  "@tailwindcss/vite": "^4.1.18"
}
```

## 🔧 Development

### Available Scripts

```bash
# Start development server with HMR
npm run dev

# Build for production
npm run build

# Run ESLint
npm run lint

# Preview production build
npm run preview
```

### Development Features

- **Hot Module Replacement (HMR)**: Instant updates during development
- **Fast Refresh**: React component updates without losing state
- **ESLint Integration**: Code quality checks
- **Tailwind CSS**: Utility-first styling

## 🏗 Build & Deployment

### Production Build

```bash
npm run build
```

This creates an optimized production build in the `dist/` folder.

### Preview Production Build

```bash
npm run preview
```

### Environment Variables

Create a `.env` file for environment-specific configuration:

```env
VITE_API_URL=http://localhost:8000
VITE_APP_NAME=Machine Maintenance Prediction
```

## ⚙️ Configuration

### Tailwind CSS

Configured in index.css with custom utilities:
- `.mechanical-card` - Card component styling
- `.status-indicator` - Status badge styling
- `.mechanical-button` - Button styling
- `.industrial-input` - Input field styling

### ESLint

Rules configured in eslint.config.js:
- React best practices
- React Hooks linting
- React Refresh compatibility
- Custom rules for variable naming

### Vite

Configuration in `vite.config.js`:
- React plugin with Babel refresh
- Optimized build settings

## 📊 Data Structure

### Machine Data
```javascript
{
  id: 'machine-id',
  name: 'Machine Name',
  type: 'CNC',
  status: 'healthy|warning|critical',
  health: 92,
  uptime: 99.5,
  temperature: 58,
  vibration: 2.8
}
```

### Sensor Reading
```javascript
{
  time: '14:30:45',
  timestamp: '2024-01-15T14:30:45Z',
  temperature: 58.5,
  vibration: 2.8,
  pressure: 125,
  rpm: 2900,
  voltage: 415,
  current: 45
}
```

### Prediction
```javascript
{
  id: 1,
  machine: 'Machine Name',
  component: 'Component Name',
  probability: 87,
  eta: '48h',
  priority: 'high|medium|low'
}
```

## 🎨 Styling

The project uses Tailwind CSS with a mechanical/industrial theme:
- Primary colors: Blue (#4f46e5)
- Secondary colors: Amber, Green, Red for status indicators
- Border radius: 8-12px for modern appearance
- Shadows: Subtle elevation for depth

## 🔐 Security Notes

- Authentication handled via Login page
- API key management in Settings
- No sensitive data stored in localStorage
- CORS considerations for API calls

## 🐛 Troubleshooting

### Port Already in Use
```bash
npm run dev -- --port 3000
```

### Clear Node Modules
```bash
rm -rf node_modules package-lock.json
npm install
```

### ESLint Errors
```bash
npm run lint -- --fix
```

## 📝 License

[Add appropriate license information]

## 👥 Contributors

[Add contributor information]

## 📞 Support

For issues, questions, or suggestions, please contact the development team.

---

**Last Updated**: January 2024  
**Version**: 0.0.0
