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
