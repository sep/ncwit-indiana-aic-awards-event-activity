# NCWIT Indiana AIC Awards — Three.js Game Arcade

High schoolers build custom 3D games using GitHub Copilot at the NCWIT Indiana AIC Awards Event. Every game is generated through an AI-powered interview — showcasing agentic coding in action.

**Live site:** `https://<your-username>.github.io/ncwit-indiana-aic-awards-event-activity/`

---

## How It Works

1. Participant opens VS Code with this repo
2. Opens Copilot Chat and says **"help me create my game"**
3. Copilot asks them questions (name, genre, colors, special features)
4. Copilot generates a complete Three.js game in a single HTML file
5. Participant plays and iterates — asking Copilot for changes
6. Facilitator pushes to GitHub → game appears on the live arcade site

## Facilitator Setup (Before the Event)

### 1. Enable GitHub Pages
- Go to repo **Settings → Pages**
- Under **Build and deployment**, select **GitHub Actions**
- The included workflow (`.github/workflows/deploy.yml`) handles deployment on push to `main`

### 2. Prepare Each Station
On each computer:
```bash
git clone https://github.com/<your-username>/ncwit-indiana-aic-awards-event-activity.git
cd ncwit-indiana-aic-awards-event-activity
code .
```

Ensure:
- VS Code is installed with **GitHub Copilot** and **GitHub Copilot Chat** extensions
- Copilot is signed in and working
- The participant has a browser open to test their game

### 3. During the Event
- Participants use Copilot Chat to create and customize games
- Periodically collect work from all stations and push:
```bash
git add -A && git commit -m "Add participant games" && git push
```
- The live site updates automatically in ~60 seconds

## Project Structure

```
├── .github/
│   ├── copilot/skills/create-game/   # Copilot skill that interviews + generates games
│   └── workflows/deploy.yml          # GitHub Pages deployment
├── games/
│   ├── _template/index.html          # Reference game template
│   ├── manifest.json                 # Registry of all participant games
│   └── <participant>/index.html      # Each participant's game
├── index.html                        # Landing page / game arcade
├── styles.css                        # Landing page styles
└── README.md
```

## For Participants

### Getting Started
1. Open **Copilot Chat** in VS Code (click the chat icon in the sidebar)
2. Type: **"help me create my game"**
3. Answer the questions Copilot asks you
4. Open your generated game file in a browser to play!
5. Keep chatting with Copilot to customize your game

### Ideas for Customization
After your game is generated, try asking Copilot:
- "Make the player a sphere instead of a cube"
- "Add a second type of enemy"
- "Make the colors more intense"
- "Add a combo multiplier for the score"
- "Make the camera follow the player"
- "Add a start screen with my name bigger"

## Tech Stack
- **Three.js** (r128) — 3D graphics, loaded from CDN
- **Vanilla HTML/JS** — no build tools, no npm
- **GitHub Pages** — free static hosting
- **GitHub Copilot** — agentic AI coding assistant
