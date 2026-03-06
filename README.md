⭐ If you are reviewing this project for the Perpova internship, please watch the 2-minute demo video first.

# 💬 Perpova Drop-In AI Chat Widget (React)

Proof-of-Work Project built for the **Software Engineer Intern** application at **Perpova Developers**.

This repository contains the **frontend chat widget** that connects to the Laravel AI backend.

The widget is designed to be embedded into any website — **WordPress, Laravel, static HTML, or custom web applications** — allowing agencies to instantly provide AI assistants for their clients.

## 🔗 Related Links

- **Backend Engine Repository**: [https://github.com/Niluminda-glitch/perpova-ai-backend](https://github.com/Niluminda-glitch/perpova-ai-backend)
- **2-Minute Demo Video**: [https://drive.google.com/file/d/1Af3cAupV3IDS9MiPpPsca6dHjE7emASo/view?usp=sharing](https://drive.google.com/file/d/1Af3cAupV3IDS9MiPpPsca6dHjE7emASo/view?usp=sharing)

## 🎯 Project Goal

This widget demonstrates how development agencies can sell **AI assistants as a service**.

Instead of building AI integrations for every client manually, agencies can:

1. Crawl the client's website
2. Generate vector embeddings
3. Deploy this widget on the website

The result is an AI assistant trained specifically on the client’s website content.

## ✨ Features

### 🎨 Modern Chat UI

Inspired by tools like Intercom and Zendesk. Features include:

- Floating action chat button
- Smooth entry animations
- Responsive design
- Clean message layout

### 🤖 AI Response Formatting

AI responses are formatted for readability. Supports:

- Paragraph formatting
- Bullet list rendering
- Preserved whitespace (`whitespace-pre-wrap`)

### ⏳ Loading Indicators

To improve user experience, the widget includes:

- "Thinking..." AI indicator
- Tailwind CSS pulse animations
- Smooth transition between messages

### 📜 Automatic Scroll Handling

New messages automatically scroll into view using:

- `useRef` + DOM manipulation

This keeps the conversation flow smooth and intuitive.

## ⚙️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Framework** | React 18 |
| **Language** | TypeScript |
| **Build Tool** | Vite |
| **Styling** | Tailwind CSS v4 |
| **Icons** | lucide-react |
| **API Requests** | Fetch API |

## 🚀 Local Development Setup

### 1️⃣ Clone Repository

```bash
git clone https://github.com/Niluminda-glitch/perpova-ai-widget.git
cd perpova-ai-widget
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Connect to Backend

Ensure the Laravel backend server is running:

`http://localhost:8000`

Inside `src/App.tsx`, verify that the API request URL points to the backend server.

### 4️⃣ Start Development Server

```bash
npm run dev
```

The development server will run at: `http://localhost:5173`

## 🧩 Deployment Vision

In production, the widget can be compiled into a single embeddable script.

Example integration:

```html
<script src="ai-widget.js"></script>
```

This allows agencies to drop AI functionality into any client website instantly.

## 👨‍💻 Author

**Kavishka Niluminda**

- **Software Engineering Student** – NIBM
- **Merit Scholar** (Rank 1 Island-wide)

- **Portfolio**: [https://www.kavishkaniluminda.me](https://www.kavishkaniluminda.me)
- **LinkedIn**: [https://www.linkedin.com/in/kavishka-niluminda-2b9a23268](https://www.linkedin.com/in/kavishka-niluminda-2b9a23268)
