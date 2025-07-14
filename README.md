# NeuroHaven
NeuroHaven – a sanctuary for the mind

TechStacks used:
**Frontend**: React (with Hooks, Redux/Context API, Tailwind CSS)
**Backend**: Spring Boot (REST APIs, security, service layers)
**Database**: MongoDB (NoSQL for flexible mood/journal structures)
**Authentication**: JWT + OAuth2 (Google Sign-In), Firebase Auth (optional fallback)
**Caching**: Redis (for sessions, mood history, etc.)
**Live Features**: WebSockets (chat with counselors or community)
**Email Service**s: SendGrid / Mailgun API
**DevOps & Cloud**:
  **Cloud**: Azure App Services + Azure Cosmos DB (Mongo-compatible)
  **CI/CD**: GitHub Actions (build → test → deploy to Azure)


App Features Breakdown
1. 👤 Authentication & Profile Management
JWT-based auth via Spring Security
Optional Google Sign-In via Firebase Auth
Roles: USER, THERAPIST, ADMIN
Azure Key Vault to manage secrets securely

2. 📅 Mood Tracker & Journaling
React UI: Slider + mood emojis
Spring Boot API to store daily mood entries
MongoDB stores {userId, moodScore, notes, timestamp}
Line chart for historical mood (using Chart.js/Recharts)

3. 🧘 Mindfulness Toolkit
Meditation audio player
Animated breathing exercises (React-based visuals)
Spring Boot fetches content from MongoDB or CMS
Push daily affirmations via Email API

4. 📚 Resource Center
React UI for filtered blog/article browsing
Admin can post articles via rich-text editor
Stored as Markdown or HTML in MongoDB

5. 💬 Live Community & Chat
React forum/discussion board
WebSocket-based private messaging
Redis Pub/Sub for real-time scalability
Moderation tools for Admin

6. 📞 Therapist Booking System
React calendar component (e.g., react-calendar)
Spring Boot to expose booking APIs
MongoDB schema for availability & sessions
Email confirmation + optional SMS via 3rd-party

7. 🔔 Reminders & Notifications
Azure Functions for scheduled reminders
Email API for mood journaling prompts
Optionally add Azure Notification Hubs (push notifications)

8. 🛠️ Admin Dashboard
Admin login via protected routes
Manage users, therapists, flagged posts
Usage analytics (page views, engagement, etc.)

📦 CI/CD with GitHub Actions & Azure
Frontend Workflow:
Build React
Deploy to Azure Static Web Apps

Backend Workflow:
Maven build & test
Deploy JAR to Azure App Service (Spring Boot)

Secrets: Stored in GitHub & Azure Key Vault

🔐 Security Considerations
Spring Security with JWT + role guards
OAuth2 support via Spring Boot starter
HTTPS enforcement via Azure configuration
CSRF protection, rate limiting, CORS filters

📊 Monitoring & Logging
Use Azure Application Insights for:
API monitoring
User behavior analytics
Error tracing (stack traces, exception maps)



Modules Overview
1. 👤 User Authentication & Profile
Signup/Login (Email, Google)
Profile creation (basic info, mental health preferences, goals)
Role-based access (Users, Therapists, Admins)

2. 📅 Mood Tracker & Journaling
Daily mood input (scale + emojis + optional journal)
Weekly/monthly visualization (charts)
Suggested exercises based on mood trends

3. 🧘 Mindfulness Exercises
Guided meditation (audio/video)
Breathing exercises (animation)
Affirmations (daily push/notifications)

4. 📚 Resource Library
Blogs, articles, videos on mental health topics
Filter by category (Anxiety, Stress, Depression, etc.)
Admin dashboard to manage resources

5. 💬 Community Forum
Public discussion threads
Anonymous posting option
Moderation tools for Admins

6. 📞 Counselor Booking System
Search verified therapists
View availability and book sessions
Video call integration (e.g., WebRTC, Zoom API)

7. 🔔 Notifications & Reminders
Mood tracking reminders
Appointment alerts
New content or community replies

8. 🛠️ Admin Dashboard
Manage users, therapists, content, and reports
Analytics and KPIs
Moderation & flagging system

🗃️ Database Schema Overview (Example for MongoDB)
Users Collection
{
  userId,
  name,
  email,
  passwordHash,
  role, // "user", "therapist", "admin"
  preferences,
  createdAt,
  updatedAt
}
Moods Collection
{
  userId,
  date,
  moodLevel,
  moodNotes,
  tags
}
Appointments Collection
{
  therapistId,
  userId,
  timeslot,
  status // "booked", "completed", "cancelled"
}

🚧 Development Phases
Phase 1: MVP (4–6 Weeks)
User auth
Mood tracker
Mindfulness page
Resource blog
Basic UI with responsive design

Phase 2: Community & Counseling (4–6 Weeks)
Forum with moderation
Booking system for therapists
Notifications

Phase 3: Scale & Enhance (4–8 Weeks)
Video chat integration
AI-based mood suggestions
Admin analytics & reporting
Mobile app (React Native / Flutter optional)

✅ Non-Functional Requirements
Responsive and mobile-friendly UI
Secure user data (HIPAA-compliant practices if possible)
Scalable microservice architecture (if using Spring Boot/Docker)
Automated testing (Jest, Postman, JUnit, etc.)
Accessibility (WAI-ARIA guidelines)

💡 Future Enhancements
AI chatbot for immediate support
Gamification (badges, streaks)
Integration with wearable devices (e.g., Fitbit, Apple Health)
