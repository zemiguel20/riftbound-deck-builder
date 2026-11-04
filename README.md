# Riftbound Deck Builder

A deck builder app, built for desktop offline use. The scope is focused solely on deck building and features that support it.

Being an offline desktop app makes it more reliable and responsive, compared to online platforms. Decks can still be exported and published to online platforms using standard formats such as deck code or text list.

> [!NOTE]
> While collection tracking might be useful for building decks with one's available card pool, collection tracking feels more natural in an online platform environment, which enables features such as trading groups. Thus, collection tracking is out of scope for now, and this app is intended for players that care little about collection features.

This deck builder aims to strongly support deck statistics (and possibly goldfish testing). A central feature is *functional categories* (e.g: draw, recursion, removal, ramp), seen in deck builders such as [Archidekt](https://archidekt.com). Dataset may contain default categories, and users can add/remove/rename categories local to the deck they are building.

## Card Data

A database file is distributed alongside the deck builder. On startup, the app checks for new versions of this file and downloads them automatically.

The card browser allows users to change cards' default categories if they wish to. These changes stay in a separate local file, so updates to the database do not delete the user's categories.

> [!NOTE]
> The card images are downloaded in the background during runtime, rather than bundling them with the app.
> The app renders a readable placeholder until the respective card image is available on the device.

## Development

### 1. Prerequisites

- [Node.js](https://nodejs.org/en) (LTS)
- [Git](https://git-scm.com/)

### 2. Setup

```bash
# Fork and clone the repository to your machine.
git clone https://github.com/zemiguel20/riftbound-deck-builder.git
# Or you can also fork it and clone your version

# Open project directory
cd riftbound-deck-builder

# Download all the required libraries
npm install
```

### 3. Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) (or [VSCodium](https://vscodium.com/)) with the following extensions:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Vue](https://marketplace.visualstudio.com/items?itemName=Vue.volar)

### 4. Technologies Overview

- **Electron:** Container allowing web technologies (HTML/CSS/JS) to run as a native desktop application. It has three main parts: *Main* (handles window creation and OS-level file access), *Renderer* (displays your website UI like a browser), and *Preload* (bridge connecting both Main and Renderer processes).
- **Vue.js:** A framework for building the website UI. Instead of manually manipulating the webpage DOM, build components that react to data/state changes.
- **Vite:** Build tool and development server.
- **Tailwind CSS:** A CSS framework with many built-in classes.
- **SQLite:** Serverless database for storing all the card data.

### 5. Folder Structure Overview (WIP)

### 6. Build

```bash
# For windows
npm run build:win

# For macOS
npm run build:mac

# For Linux
npm run build:linux
```

### 7. Updating Card Data

The source does not store the whole catalog. Instead, it contains a script that downloads and processes the latest catalog from [OpenRift](https://openrift.app/developers), generates a copy with this app's schema, and finally generates the database file.

There is a `default-categories.json` file in the repo, where the default categories for each card are authored. This file sits in the repository alongside the script. The script then joins this data while creating the database.

The updated database file is uploaded together with a manifest file.