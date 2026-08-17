# IU Student Assistant - Specification Document

## 1. Concept & Vision

IU Student Assistant is a sleek, professional student portal for Iqra University students that combines academic information management with an intelligent AI chatbot. The application feels like a premium EdTech product—clean, efficient, and genuinely helpful. It's designed to be the single destination for students to check their schedule, calculate GPA, track attendance, and get instant answers to academic questions.

The personality is professional yet approachable, with subtle futuristic touches that hint at the AI capabilities without being gimmicky.

## 2. Design Language

### Aesthetic Direction
Modern academic dashboard with a hint of fintech polish. Think Notion meets a premium banking app—clean surfaces, purposeful whitespace, and information hierarchy that guides the eye naturally.

### Color Palette
**Light Mode:**
- Primary: `#2563EB` (Royal Blue - trust, education)
- Primary Dark: `#1D4ED8`
- Secondary: `#7C3AED` (Purple - AI/tech accent)
- Accent: `#10B981` (Emerald - success/positive)
- Warning: `#F59E0B` (Amber)
- Danger: `#EF4444` (Red)
- Background: `#F8FAFC`
- Surface: `#FFFFFF`
- Text Primary: `#1E293B`
- Text Secondary: `#64748B`
- Border: `#E2E8F0`

**Dark Mode:**
- Primary: `#3B82F6`
- Primary Dark: `#2563EB`
- Secondary: `#8B5CF6`
- Accent: `#34D399`
- Warning: `#FBBF24`
- Danger: `#F87171`
- Background: `#0F172A`
- Surface: `#1E293B`
- Text Primary: `#F1F5F9`
- Text Secondary: `#94A3B8`
- Border: `#334155`

### Typography
- **Headings:** Inter (700, 600) - clean, professional
- **Body:** Inter (400, 500) - highly readable
- **Monospace:** JetBrains Mono - for codes, IDs
- **Scale:** 12px / 14px / 16px / 18px / 24px / 32px / 48px

### Spatial System
- Base unit: 4px
- Spacing scale: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64px
- Card padding: 24px
- Section gaps: 32px
- Border radius: 8px (small), 12px (medium), 16px (large)

### Motion Philosophy
- Transitions: 200ms ease-out (default), 300ms ease-in-out (page transitions)
- Hover effects: subtle lift (translateY -2px) with shadow enhancement
- Loading states: pulse animation for skeletons
- Chat messages: slide-in from bottom with fade (300ms)
- Page transitions: fade-in (200ms)

### Visual Assets
- Icons: Lucide React (consistent 24px size, 1.5px stroke)
- No stock photos - pure UI with gradients and icons
- Decorative: Subtle gradient overlays, soft shadows

## 3. Layout & Structure

### Overall Architecture
- Sidebar navigation (280px width on desktop, collapsible)
- Main content area with max-width 1400px
- Fixed header with user profile and theme toggle
- Mobile: Bottom navigation or hamburger menu

### Page Structure
1. **Dashboard**: Stats grid → Today's Schedule → Quick Actions
2. **IU Assistant**: Full-height chat interface with suggestions sidebar
3. **Timetable**: Filter bar → Weekly grid view
4. **GPA Calculator**: Course form → Results card → History
5. **Courses**: Filter bar → Course cards grid
6. **Attendance**: Course list with progress bars
7. **Exams**: Exam cards with countdown badges
8. **Profile**: Profile header → Info cards

### Responsive Strategy
- Desktop (≥1024px): Full sidebar, multi-column layouts
- Tablet (768-1023px): Collapsible sidebar, 2-column grids
- Mobile (<768px): Bottom nav or hamburger, single column, stacked cards

## 4. Features & Interactions

### A. Dashboard
- Personalized greeting based on time of day
- 5 stat cards with icons and trend indicators
- Today's schedule with status badges (In Progress, Upcoming, Completed)
- Quick action buttons to other sections
- Next class countdown

### B. IU Assistant Chatbot
- Rule-based responses using keyword matching
- Mock data integration for personalized answers
- Typing indicator (300ms delay before responses)
- Message timestamps
- Suggested questions as clickable chips
- Clear chat button
- Scrollable message history
- Auto-scroll to latest message

### C. Timetable Page
- Weekly view with day tabs
- Course cards showing code, name, instructor, time, room
- Filter by day, course, semester
- "Ask IU Assistant" floating button

### D. GPA Calculator
- Add/remove courses dynamically
- Grade selector dropdown (A+ to F)
- Credit hours input (1-6)
- Real-time GPA calculation
- Visual grade display
- Reset functionality
- Save/load calculated GPA

### E. Courses Page
- Course cards with all details
- Progress indicators for attendance
- Instructor info with icons
- Filter by semester/course

### F. Attendance Page
- Course-wise attendance with progress bars
- Color-coded status (green >90%, yellow >75%, red ≤75%)
- Warning indicators for low attendance
- Overall attendance summary

### G. Exams Page
- Exam cards with countdown badges
- Exam type badges (Midterm, Final, Quiz)
- Date/time/room information
- "Days remaining" calculated dynamically

### H. Profile Page
- Profile header with avatar
- Student info card
- Academic info card
- Contact info card
- Edit button (visual only for now)

### I. Global Features
- Dark/Light mode toggle with localStorage persistence
- Global search (header)
- Responsive sidebar collapse
- Smooth page transitions

## 5. Component Inventory

### StatCard
- States: default, loading, hover
- Shows: icon, label, value, optional trend
- Hover: subtle lift with enhanced shadow

### ScheduleCard
- Shows: course name, code, time, room, teacher, status
- Status badge: Completed (gray), In Progress (blue pulse), Upcoming (default)

### ChatMessage
- User: right-aligned, primary color background
- Assistant: left-aligned, surface background
- Timestamp below each message

### CourseCard
- Course code badge
- Course name, instructor, details
- Attendance indicator
- Hover: lift effect

### ExamCard
- Exam type badge
- Course name, date, time, room
- Countdown badge
- Hover: subtle scale

### Sidebar
- Logo and app name
- Nav items with icons
- Active state indicator
- Collapse button
- Mobile: slide-in drawer

### Button
- Variants: primary, secondary, ghost, danger
- States: default, hover, active, disabled, loading
- Sizes: sm, md, lg

### Input
- States: default, focus, error, disabled
- Label and helper text support

### ProgressBar
- Animated fill
- Color based on percentage
- Label showing percentage

## 6. Technical Approach

### Stack
- React 18 with Vite
- React Router v6 for navigation
- Lucide React for icons
- Vanilla CSS with CSS custom properties (no Tailwind per requirements)
- localStorage for theme persistence

### Architecture
```
src/
├── components/
│   ├── Layout/
│   │   ├── Sidebar.jsx
│   │   ├── Header.jsx
│   │   └── Layout.jsx
│   ├── UI/
│   │   ├── Button.jsx
│   │   ├── Card.jsx
│   │   ├── Input.jsx
│   │   ├── Select.jsx
│   │   ├── ProgressBar.jsx
│   │   └── Badge.jsx
│   ├── Dashboard/
│   │   ├── StatCard.jsx
│   │   ├── ScheduleCard.jsx
│   │   └── QuickActions.jsx
│   ├── Chatbot/
│   │   ├── ChatMessage.jsx
│   │   ├── ChatInput.jsx
│   │   └── SuggestedQuestions.jsx
│   ├── Timetable/
│   │   └── TimetableCard.jsx
│   └── Course/
│       ├── CourseCard.jsx
│       └── AttendanceRow.jsx
├── pages/
│   ├── Dashboard.jsx
│   ├── Assistant.jsx
│   ├── Timetable.jsx
│   ├── GPACalculator.jsx
│   ├── Courses.jsx
│   ├── Attendance.jsx
│   ├── Exams.jsx
│   └── Profile.jsx
├── data/
│   └── studentData.js
├── services/
│   └── chatbotService.js
├── hooks/
│   ├── useTheme.js
│   └── useChatbot.js
├── styles/
│   ├── variables.css
│   ├── reset.css
│   └── global.css
├── utils/
│   └── helpers.js
├── App.jsx
└── main.jsx
```

### Data Model
All data in `studentData.js`:
- student: { id, name, email, program, department, campus, semester, avatar }
- courses: [{ id, code, name, instructor, credits, section, timing, room, attendance }]
- schedule: [{ day, courseId, startTime, endTime, room }]
- exams: [{ id, courseId, type, date, time, room }]
- grades: [{ courseId, grade, credits }]

### Chatbot Service
- Keyword-based intent recognition
- Mock data queries for personalized responses
- Structured response templates
- Fallback for unrecognized queries
- Easy to extend with API integration later

## 7. Quality Checklist

- [ ] All navigation links work
- [ ] All pages load without errors
- [ ] GPA calculator computes correctly
- [ ] Chatbot responds to all documented queries
- [ ] Dark/light mode toggles and persists
- [ ] Responsive on all breakpoints
- [ ] No console errors
- [ ] All imports resolved
- [ ] Smooth animations
- [ ] Accessible (basic ARIA labels)
