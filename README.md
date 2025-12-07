OBE Management System (PyGenicArc Template)
A comprehensive Outcome Based Education (OBE) Management System built with React, Material UI, and Tailwind CSS. This application facilitates the management of academic curriculum, assessments, and the automated calculation of Course Outcome (CO) and Program Outcome (PO) attainment.
It features a role-based architecture (Super Admin, Admin/HOD, Faculty) and includes a mock backend using json-server for rapid development and demonstration.
________________________________________
🚀 Features
👨‍🏫 Faculty Module
•	Dashboard: Overview of assigned courses and student statistics.
•	Course Configuration: Define Course Outcomes (COs), Blooms Taxonomy levels, and map them to syllabus modules.
•	Assessment Planning: Configure Internal Assessments (IA), Assignments, and Semester End Exams (SEE) with specific CO mappings and weightages.
•	Articulation Matrix: Interactive interface to map COs to POs and PSOs (Program Specific Outcomes).
•	Marks Entry: Excel-like interface for entering student marks for various assessments. Supports CSV Bulk Upload.
•	Attainment Reports: Real-time visualization (Bar Charts) of CO and PO attainment levels.
•	Indirect Assessment: Manage Course End Surveys to calculate indirect attainment.
👮‍♂️ Department Admin (HOD) Module
•	Department Dashboard: Statistics on faculty, courses, and department performance.
•	Resource Management: Manage Faculty and Courses (Add, Edit, Delete).
•	Course Assignment: Assign courses to specific faculty members for the semester.
•	Outcome Management: Define and manage Program Outcomes (POs) and PSOs.
•	Configuration: Set global attainment rules (thresholds, weightages for Direct/Indirect attainment).
•	Consolidated Reports: View Program Level Matrices and consolidated evaluation results across all courses.
⚡ Super Admin Module
•	Institution Dashboard: High-level overview of all departments.
•	Department Management: Create and manage academic departments.
•	Admin Management: Create Department Admins (HODs) and assign them to departments.
________________________________________
🛠️ Tech Stack
•	Frontend Framework: React (Vite)
•	UI Component Library: Material UI (MUI) v6
•	Styling: Tailwind CSS & Emotion
•	Routing: React Router v6
•	State Management: React Context API
•	Charts: Recharts & ECharts
•	Icons: Lucide React & Material Icons
•	Mock Backend: JSON Server
•	HTTP Client: Axios
________________________________________
⚙️ Installation & Setup
This project requires Node.js to be installed on your machine.
1. Clone the repository
Bash
git clone <repository-url>
cd <project-folder>
2. Install Dependencies
Bash
npm install
3. Setup Concurrent Running (Recommended)
To run both the frontend and the mock backend in a single command, install concurrently:
Bash
npm install concurrently --save-dev
Then update your package.json scripts section to look like this:
JSON
"scripts": {
  "dev": "vite",
  "server": "json-server --watch db.json --port 3001",
  "start": "concurrently \"npm run server\" \"npm run dev\""
}
4. Run the Application
Option A: Single Command (if step 3 was followed)
Bash
npm start
Option B: Separate Terminals
Open two terminal windows:
Terminal 1 (Backend):
Bash
npm run server
Terminal 2 (Frontend):
Bash
npm run dev
The application will launch at http://localhost:5173 (or the port shown in your terminal).
The mock API will run at http://localhost:3001.
________________________________________
🔑 Default Credentials
The project comes pre-seeded with mock data. You can use the Quick Login buttons on the login page or use these credentials:
Role	Email	Password
Super Admin	superadmin@obe.com	any
Admin (CSE)	admin@obe.com	any
Faculty	faculty@obe.com	any
(Note: The login logic currently accepts any non-empty password).
________________________________________
📂 Project Structure
src/
├── app/
│   ├── components/       # Reusable UI components (Layout, Navbar, Cards)
│   ├── contexts/         # Global state (Auth, Settings, Notifications)
│   ├── hooks/            # Custom React hooks
│   ├── services/         # API configuration (Axios)
│   ├── utils/            # Constants and helper functions
│   ├── views/
│   │   ├── dashboard/    # General dashboards
│   │   ├── sessions/     # Login pages
│   │   └── marks-management/
│   │       ├── Admin/        # Admin specific pages
│   │       ├── Faculty/      # Faculty specific pages
│   │       ├── SuperAdmin/   # Super Admin pages
│   │       └── shared/       # Shared view components
│   ├── navigations.js    # Sidebar navigation config
│   └── routes.jsx        # App routing definition
├── assets/               # Static assets
└── main.jsx              # Entry point
________________________________________
🎨 Configuration
Attainment Rules
Admins can configure the OBE calculation logic under Admin > System Configuration.
•	Thresholds: Set the percentage required for a student to "pass" a CO.
•	Weightages: Adjust the split between Internal (CIE) and External (SEE) marks.
•	Direct/Indirect: Adjust the weightage for the final PO calculation (e.g., 80% Direct + 20% Indirect).
Theming
The project uses a custom theme engine located in src/app/components/parcTheme. You can customize colors in themeColors.js or adjust layout settings in Layout1Settings.js.
________________________________________
📝 License
This project is licensed under the MIT License.

