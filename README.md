# iVakya LQA Tracker

> **Localization Quality Assurance** — a single-file web application for tracking LQA workflows, relay statuses, Zendesk tickets, and implementation progress across 100+ locales.

---

## 📸 Screenshot

> _Place a screenshot of the application here._
> Suggested path: `assets/screenshot.png`
>
> ```
> ![iVakya LQA Tracker Screenshot](assets/screenshot.png)
> ```

---

## 📋 Overview

**iVakya LQA Tracker** is a browser-based productivity tool built as a self-contained `index.html` file. It connects to a **Supabase** backend for real-time data persistence and user authentication, allowing LQA teams to manage translation quality reviews in a structured, collaborative environment.

---

## ✨ Features

### 🔐 Authentication
- Supabase-powered login screen with role-based user display
- Session timer visible in the top bar
- Secure sign-out

### 📊 Tracker Modules
Each tracker row captures the full lifecycle of an LQA task:

| Field | Description |
|---|---|
| Sl No | Serial number |
| Recd Date | Date received |
| Requestor | Dropdown of known requestors |
| Live / Retro | Task type selector |
| Project Name & No | Project identifiers |
| Relay | Relay reference |
| Source / Target | Locale selectors (100+ locales) |
| Translation Team | Name, email, Jira user |
| Reviewer Team | Name, email, Jira user |
| Jira Link | Direct link to Jira ticket |
| LQA Status | Heads up → Closed → Arbitration, etc. |
| Score | Quality score |
| Relay Status | PO issued / In progress / Complete |
| Implementation Status | Done by Reviewer / Done by Translator |
| ZD Ticket | Zendesk ticket reference |
| ZD Ticket Status | Open / Pending / Closed |
| Start / Due / Final Deadline | Date tracking |
| Comments | Free-text notes |

### 📥 Import / Export
- **Import** `.xlsx` or `.csv` files — columns auto-matched by name
- Drag-and-drop file upload with 3-row preview
- **Export current tracker** as Excel/CSV
- **Export All** — bundles every tracker into a single Excel file for month-end archiving

### 📈 Dashboard & Analytics
- Built-in **Chart.js** charts for visual status breakdowns
- Summary stat cards per tracker

### 🖥️ Excel-like Spreadsheet View
- Full-screen spreadsheet overlay with row/column headers
- Cell selection, range highlighting, and inline editing
- Sheet tab navigation
- Context menu (right-click) for row operations

### 🌙 Dark Mode
- Full dark theme with `data-theme="dark"` toggle
- Crisp near-black palette with orange accent (`#E8692A`)
- Persisted via UI toggle button

### 📱 Responsive Design
| Breakpoint | Behaviour |
|---|---|
| ≥ 1280px | Full sidebar + all toolbar actions |
| 1100–1279px | Compact sidebar, reduced font sizes |
| 768–1099px | Sidebar as slide-in drawer |
| < 768px | Drawer + fixed bottom action bar |

### 🗑️ Month-End Reset
- "Clear All Data" wipes all rows across every tracker
- Confirmation modal with a hard-delete warning
- Intended for monthly archiving workflow

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML / CSS / JavaScript (single file) |
| Database & Auth | [Supabase](https://supabase.com) |
| Charts | [Chart.js 4.4](https://www.chartjs.org) |
| Spreadsheet | [SheetJS / XLSX 0.18](https://sheetjs.com) |
| Fonts | Inter, JetBrains Mono, Geist (Google Fonts) |

---

## 🚀 Getting Started

### Prerequisites
- A modern browser (Chrome, Firefox, Edge, Safari)
- A **Supabase** project with the relevant tables and user accounts set up

### Running Locally

```bash
# No build step required — just open the file
open index.html
```

Or serve it with any static file server:

```bash
npx serve .
# then visit http://localhost:3000
```

### Supabase Configuration

Inside `index.html`, locate the Supabase initialisation block and replace the placeholder values:

```js
const supabase = Supabase.createClient(
  'YOUR_SUPABASE_URL',
  'YOUR_SUPABASE_ANON_KEY'
);
```

> ⚠️ Never commit your Supabase service-role key to a public repository.

---

## 📁 Project Structure

```
.
├── index.html        # Entire application — HTML, CSS, and JS in one file
├── README.md         # This file
└── assets/           # (optional) Screenshots, icons, exports
    └── screenshot.png
```

---

## 🌐 Supported Locales

The tracker includes a built-in locale picker covering 100+ language-region pairs, including:

`af_ZA`, `ar_AE`, `ar_SA`, `de_DE`, `en_US`, `en_GB`, `es_ES`, `es_MX`, `fr_FR`, `hi_IN`, `ja_JP`, `ko_KR`, `pt_BR`, `ru_RU`, `zh_CN`, `zh_TW` … and many more.

---

## 🔑 User Roles

After login, each user's **name** and **role** are displayed in the top-right corner. Role-based display is driven by Supabase user metadata.

---

## 📦 LQA Status Values

| Status | Meaning |
|---|---|
| Heads up | Task flagged, not yet started |
| Reviewer available | Reviewer assigned |
| Review in progress | Active review underway |
| Translator Assessment | Under translator review |
| Closed | Review complete |
| Arbitration | Dispute raised |
| Escalation | Escalated for resolution |

---

## 🤝 Contributing

1. Fork this repository
2. Create a feature branch: `git checkout -b feature/my-change`
3. Commit your changes: `git commit -m "Add my change"`
4. Push to the branch: `git push origin feature/my-change`
5. Open a Pull Request

---

## 📄 License

© iVakya. All rights reserved.
