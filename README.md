# ConnectPro 🌐

**ConnectPro** is a professional networking web application I developed to help bridge the gap between experienced (senior) professionals and emerging (junior) talent. The platform allows users to create detailed profiles, search for mentors or mentees, and establish connections for career growth and mentorship.

This project reflects my passion for building purposeful tech solutions that drive real impact — especially in education, mentorship, and career development.

---

## 🚀 What It Does

- ✨ **Create and Browse Profiles:** Users can create a profile with details like name, skills, experience, bio, and role.
- 🔍 **Smart Filtering:** Search and filter profiles by industry, skill, and experience level (junior or senior).
- 🔗 **Mentorship Connections:** Users can send connection requests for mentorship and networking.
- 📷 **QR Code Feature:** Each profile has a unique QR code for easy sharing and instant access.
- 📱 **Responsive Design:** Looks great on mobile and desktop using Tailwind CSS.
- ⚡ **Real-time UI:** Built with modern tools for smooth user experience and instant updates.

---

## 🛠️ Tech Stack

### Frontend
- React 18 + TypeScript
- Tailwind CSS
- Wouter (for routing)
- shadcn/ui + Radix UI (for accessible UI components)
- TanStack Query (server state)
- Zod + React Hook Form (form validation)

### Backend
- Node.js + Express.js
- PostgreSQL (primary DB)
- Drizzle ORM
- Zod for input validation
- ES Modules and Vite (tooling)

---

## 📁 Project Folder Structure


├── client/ # Frontend React code
│ └── src/
│ ├── components/
│ ├── pages/
│ ├── hooks/
│ ├── lib/
├── server/ # Express backend
│ ├── index.ts
│ ├── routes.ts
│ ├── storage.ts
├── shared/ # Shared schemas and types
│ └── schema.ts


---

## 🔗 API Endpoints

**Profiles**
- `GET /api/profiles` → All profiles  
- `GET /api/profiles/level/:level` → By experience (junior/senior)  
- `POST /api/profiles` → Create profile  
- `PUT /api/profiles/:id` → Update profile  

**Connections**
- `POST /api/connections` → Send request  
- `GET /api/profiles/:id/connections` → Get connections  
- `PUT /api/connections/:id` → Update status  

---

## 🧪 Sample Data

Includes a set of pre-seeded users:
- **Seniors**: Software Engineer, Product Manager, Marketing Director
- **Juniors**: Frontend Developer, UX Designer, Marketing Analyst

Great for testing functionality and design flow.

---

## ⚙️ Installation

```bash
# Clone the repo
git clone https://github.com/Vishugarg2/Senior-Junior-Link.git
cd Senior-Junior-Link

# Install dependencies
npm install

# Start the app
npm run dev

🌈 Design Theme
Primary Blue (#4F7FF0) – Trust and professionalism

Accent Green (#10B981) – Growth and mentorship

Background Gray (#F9FAFB) – Clean and minimal layout


🙋‍♀️ About Me
Hi! I'm Vaishali Garg, a third-year Electrical and Computer Engineering student at Thapar Institute. I'm passionate about tech, learning by building, and creating real-world solutions that matter.

🔗 GitHub: @Vishugarg2

📧 Email: vaishlaigarg2607@gmail.com

🙏 Acknowledgements
shadcn/ui – UI components

Lucide Icons – Icon set

DiceBear API – Avatar generator

Inspiration: The idea of mentorship-driven networks for student success

