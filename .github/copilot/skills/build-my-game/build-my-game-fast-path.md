# Build My Game Fast Path

Use this as the operational fast path for /build-my-game runs.

- Start with vscode_askQuestions immediately.
- Ask the first question exactly as: What is your name?
- Use a single vscode_askQuestions call for the interview.
- Ask ALL of the following questions in a single vscode_askQuestions call, in this exact order and wording (verbatim). Use the option lists from SKILL.md § "Step 1: Interview the Participant" for each question's choices:

  1. **Your Name** — "What's your name? (This will be used for your game's folder and credits)"
  2. **Game Genre** — "Pick a game type!" (options from SKILL.md)
  3. **Game Setting** — "What world does your game live in?" (options from SKILL.md)
  4. **Color Theme** — "Pick a vibe!" (options from SKILL.md)
  5. **Special Feature** — "Want to add a twist? Pick one or describe your own!" (options from SKILL.md)
  6. **Game Title** — "Now that you know what your game is about, what do you want to call it?"

- Ask for the game title last, after gameplay and theme questions.
- Keep the interview tone friendly and supportive.
- Do not paraphrase or reword any required interview question text.
- If the askQuestions dialog is cancelled, do not edit files and retry using the same verbatim questions when the user resumes.
- Minimal required files after interview: games/_template/index.html and games/manifest.js.
- Fast-path file references SKILL.md for option lists — do not duplicate them.
- Avoid reading README.md, index.html, and styles.css unless the user asks to change the arcade site or docs.
- New participant games live at games/<filesystem-safe-name>/index.html.
- Games are single-file HTML with inline JS/CSS and Three.js r128 from CDN.
- Game styling stays inside each participant file; do not create per-game CSS files or modify root index.html/styles.css unless the user asks for arcade-site changes.
- GAME DESIGN RULES:
  - Do NOT default to runner/side-scroller mechanics. Platform games should use the full 2D/3D plane (movement in all directions), not just left-to-right scrolling.
  - Each game must be conceptually unique — do NOT reuse mechanics, layouts, or patterns from other generated games. Treat each game as a fresh design.
  - Encourage use of the entire play area (arena-style, open-world, multi-directional movement) rather than constrained corridors or auto-scrolling.
  - Every game must display instructions on the title screen so players know how to play before starting.
  - Every game must support both keyboard controls (desktop) AND on-screen touch controls (mobile). Use `@media (pointer: coarse)` to show touch buttons only on touch devices. Title/game-over screens must respond to both SPACE and tap.
- The manifest is games/manifest.js (NOT .json) — format: `const GAMES = [{title, author, path, genre?, color?}, ...]`
- index.html loads manifest.js via `<script src="games/manifest.js">` (no fetch; works with file:// protocol).
- After generating the game and updating the manifest, open the participant's game in Chrome by running: `open -a "Google Chrome" games/<their-folder>/index.html`
