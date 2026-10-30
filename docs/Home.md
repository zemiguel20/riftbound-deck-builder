# Development Documentation

## 1. Prerequisites

- [Node.js](https://nodejs.org/en) (LTS)
- [Git](https://git-scm.com/)

Run these commands in the terminal to check if they were installed properly. If yes, the version numbers should be printed.

```bash
node -v
git -v

# Output example:
# v24.22.1
# git version 2.43.0
```

## 2. Setup

```bash
# Fork and clone the repository to your machine
# Replace <your-username>, or simply copy the clone link provided by your forked repository.
git clone https://github.com/<your-username>/riftbound-deck-builder.git
cd riftbound-deck-builder

# Download all the required libraries specified in `package.json`
npm install
```

### 2.1 Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) (or [VSCodium](https://vscodium.com/)) with the following extensions:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Vue](https://marketplace.visualstudio.com/items?itemName=Vue.volar)

## 3. Architecture and Directory Structure Overview

- **Electron:** Acts as the desktop container. It allows web technologies (HTML/CSS/JS) to run as a native desktop application. It splits code into a _Main Process_ (handles window creation and OS-level file access) and _Renderer Processes_ (displays your UI just like a website in a browser).
- **Vue.js:** A frontend framework. Instead of manually manipulating the webpage DOM, Vue lets you build components that react to data/state changes.
- **Vite:** Build tool and development server.
- **Tailwind CSS:** A CSS framework with many built-in classes.
- **SQLite:** An embedded database with all the card data.

```
riftbound-deck-builder/
├── src/                   # Source code
│   ├── main/              # Electron Main Process (Node.js code, window spawning)
│   ├── preload/           # Bridge script safely connecting Main and Renderer processes
│   └── renderer/          # Frontend code (Your Vue application)
│       ├── assets/        # Images, fonts, raw styling
│       ├── components/    # Reusable Vue components (Card, DeckList, FilterBar)
│       ├── views/         # Full page layouts (DeckBuilderView, HomeView)
│       ├── App.vue        # Root Vue component
│       └── main.ts        # Entry point where Vue mounts to the DOM
├── package.json           # Project metadata, dependencies, and CLI scripts
└── (other config files)
```

## 4. Build

```bash
# For windows
npm run build:win

# For macOS
npm run build:mac

# For Linux
npm run build:linux
```