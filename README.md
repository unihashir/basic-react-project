# IU Student Assistant

<div align="center">
  <img src="public/favicon.svg" alt="IU Student Assistant Logo" width="80" />
  
  **Your Smart Iqra University Student Companion**

  A professional React.js student portal with AI chatbot capabilities.

  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![React](https://img.shields.io/badge/React-18-blue.svg)](https://reactjs.org/)
  [![Vite](https://img.shields.io/badge/Vite-5.0-brightgreen.svg)](https://vitejs.dev/)
</div>

---

## 📋 Features

### Core Features

- **📊 Dashboard** - Personalized student dashboard with GPA, attendance, and today's schedule
- **🤖 IU Assistant** - AI chatbot to answer academic questions about schedule, courses, GPA, and more
- **📅 Timetable** - Weekly class schedule with day and course filters
- **🧮 GPA Calculator** - Calculate semester GPA with course grades and credit hours
- **📚 Courses** - View enrolled courses with details and attendance
- **✅ Attendance** - Track attendance percentage for each course
- **📝 Exams** - View upcoming exams with countdown timers
- **👤 Profile** - Student profile with academic information

### Smart Features

- **Natural Language Chatbot** - Ask questions in plain English
- **Dark/Light Mode** - Theme toggle with persistence
- **Responsive Design** - Works on desktop, tablet, and mobile
- **Real-time Calculations** - GPA updates as you add grades
- **Attendance Warnings** - Alerts for courses below 75%

---

## 🛠️ Technologies Used

- **Frontend Framework**: React.js 18
- **Build Tool**: Vite 5
- **Routing**: React Router v6
- **Icons**: Lucide React
- **Styling**: CSS3 with CSS Custom Properties (Variables)
- **Fonts**: Inter (Google Fonts)

---

## 📁 Project Structure

```
src/
├── components/
│   ├── Layout/
│   │   ├── Sidebar.jsx        # Navigation sidebar
│   │   ├── Header.jsx         # Top header with search
│   │   └── Layout.jsx        # Main layout wrapper
│   ├── UI/
│   │   ├── Card.jsx           # Reusable card component
│   │   ├── Badge.jsx          # Badge/status component
│   │   └── ProgressBar.jsx    # Progress indicator
│   ├── Dashboard/
│   │   ├── StatCard.jsx       # Statistics card
│   │   └── ScheduleCard.jsx  # Class schedule card
│   └── Chatbot/
│       ├── ChatMessage.jsx    # Chat message bubble
│       ├── ChatInput.jsx      # Message input field
│       └── SuggestedQuestions.jsx  # Quick action buttons
│
├── pages/
│   ├── Dashboard/             # Main dashboard page
│   ├── Assistant/             # AI chatbot page
│   ├── Timetable/             # Weekly schedule page
│   ├── GPACalculator/         # GPA calculation page
│   ├── Courses/               # Courses listing page
│   ├── Attendance/            # Attendance tracking page
│   ├── Exams/                 # Exams schedule page
│   └── Profile/               # Student profile page
│
├── data/
│   └── studentData.js         # Mock student data
│
├── services/
│   └── chatbotService.js      # Rule-based chatbot logic
│
├── styles/
│   ├── variables.css          # CSS custom properties
│   ├── reset.css              # CSS reset/normalize
│   └── global.css             # Global styles
│
├── App.jsx                    # Main app with routing
└── main.jsx                   # Entry point
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 16+ installed
- npm or yarn package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd iu-student-assistant
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm run dev
   ```

4. **Open in browser**
   ```
   http://localhost:5173
   ```

### Build for Production

```bash
npm run build
```

The built files will be in the `dist` folder.

---

## 🤖 How the Chatbot Works

The IU Assistant chatbot uses a **rule-based intent recognition system** to understand and respond to student queries.

### Current Capabilities

| Query Type | Examples | Response |
|------------|----------|----------|
| **Greeting** | "Hi", "Hello" | Friendly welcome message |
| **GPA/CGPA** | "What's my GPA?", "Show my grades" | Displays current GPA & CGPA |
| **Schedule** | "Today's schedule", "Classes tomorrow" | Lists scheduled classes |
| **Courses** | "What courses am I taking?" | Shows enrolled courses |
| **Attendance** | "My attendance", "How's my attendance?" | Attendance percentages |
| **Credits** | "How many credit hours?", "Total credits" | Credit hour summary |
| **Next Class** | "When is my next class?", "Upcoming class" | Next class details |
| **Exams** | "When are my exams?", "Upcoming exams" | List of upcoming exams |
| **Profile** | "My profile", "About me" | Student information |
| **Help** | "Help", "What can you do?" | List of available commands |

### Architecture

The chatbot is structured for easy extensibility:

```
1. User Input → Intent Recognition (regex patterns)
2. Intent → Response Generator
3. Response Generator → Mock Data Lookup
4. Response → UI Display
```

### Future Enhancements

The chatbot architecture is designed to easily integrate:
- **OpenAI GPT API** - For more natural conversations
- **Firebase** - For real-time data
- **University API** - For real student data
- **Custom Training** - For IU-specific responses

---

## 🎨 Design System

### Color Palette

**Light Mode:**
- Primary: `#2563EB` (Royal Blue)
- Secondary: `#7C3AED` (Purple)
- Success: `#10B981` (Emerald)
- Warning: `#F59E0B` (Amber)
- Danger: `#EF4444` (Red)

**Dark Mode:**
- All colors have dark mode variants with appropriate contrast

### Typography

- **Headings**: Inter Bold (700)
- **Body**: Inter Regular (400)
- **Monospace**: JetBrains Mono

### Components

- Cards with hover effects
- Badges for status indicators
- Progress bars for percentages
- Responsive grids
- Smooth transitions

---

## 📱 Responsive Design

| Breakpoint | Layout |
|------------|--------|
| Desktop (≥1024px) | Full sidebar, multi-column grids |
| Tablet (768-1023px) | Collapsible sidebar, 2-column grids |
| Mobile (<768px) | Bottom/hamburger nav, single column |

---

## 🔮 Future Improvements

- [ ] Connect to real university database
- [ ] Student authentication system
- [ ] Push notifications for reminders
- [ ] Calendar integration
- [ ] Grade prediction using AI
- [ ] Study planner assistant
- [ ] Assignment tracker
- [ ] Online payment integration
- [ ] Library card integration
- [ ] Bus/tram schedule
- [ ] Real-time chat with AI using GPT
- [ ] Dark mode for chatbot
- [ ] Export grades as PDF
- [ ] Mobile app (React Native)

---

## 👨‍💻 Developer

Built with ❤️ for Iqra University students

**Technologies Used:**
- React.js 18
- Vite 5
- React Router 6
- Lucide React Icons
- CSS3 Custom Properties

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Iqra University for the inspiration
- All students who provided feedback
- Open source community for amazing tools

---

<div align="center">
  <strong>Made with ❤️ for IU Students</strong>
  
  *Your academic success is our priority*
</div>
