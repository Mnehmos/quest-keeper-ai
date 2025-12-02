# Quest Keeper AI

**The first AI-powered tabletop RPG platform combining an AI Dungeon Master with 3D battlemap visualization and complete game state management.**

![Status](https://img.shields.io/badge/status-alpha-yellow)
![License](https://img.shields.io/badge/license-Apache%202.0-blue)
![MCP Tools](https://img.shields.io/badge/MCP%20tools-80+-brightgreen)

## 🎮 What is Quest Keeper AI?

Quest Keeper AI bridges the gap between **pure narrative AI tools** (like AI Dungeon—great storytelling, zero tracking) and **pure mechanical trackers** (like D&D Beyond—excellent sheets, no AI). 

**The key insight:** The AI describes the world, but the engine defines it. LLMs never lie about your HP, inventory, or quest progress because all state comes from a verified database.

## 🖥️ Two Ways to Play

### Desktop App (Full Experience)
A complete Tauri application with:
- React frontend with dual-pane interface (chat + viewport)
- Three.js 3D battlemap with creature tokens and terrain
- Character sheets, inventory, world state views
- Multi-LLM support (Claude, GPT, Gemini, OpenRouter)
- Bundled database with Fellowship of the Ring content

### MCP Backend Only
Use `rpg-mcp` with any MCP-compatible client:
- **[Claude Desktop](https://claude.ai/download)** - Native MCP support
- **[KiloCode](https://kilocode.ai)** - VS Code extension
- **[RooCode](https://roocode.com)** - AI development environment

📖 **[Quick Start Guide](https://questkeeperai.com/quickstart)** - Setup instructions for both options

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    QUEST KEEPER AI                          │
│                                                             │
│  ┌──────────────────────┐    ┌────────────────────────────┐│
│  │    TAURI SHELL       │    │     REACT FRONTEND         ││
│  │  (Native Desktop)    │    │  ┌──────────┬───────────┐  ││
│  │                      │    │  │ Terminal │  Viewport │  ││
│  │  - Window mgmt       │    │  │ (Chat)   │ - 3D Map  │  ││
│  │  - File system       │    │  │          │ - Sheets  │  ││
│  │  - Sidecar spawn     │    │  │          │ - Inv.    │  ││
│  └──────────┬───────────┘    │  └──────────┴───────────┘  ││
│             │                └────────────────────────────┘│
│             │ Spawn                                        │
│             ▼                                              │
│  ┌──────────────────────────────────────────────────────┐  │
│  │              RPG-MCP SERVER (80+ Tools)              │  │
│  │  Characters • Inventory • Combat • Quests • Worlds   │  │
│  │  Dice • Secrets • Grand Strategy • Turn Management   │  │
│  │                     SQLite DB                        │  │
│  └──────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

## ✨ Features

### Core Systems
- **Full D&D 5e Mechanics** - Stats, skills, combat, advancement
- **3D Spatial Battlemap** - React Three Fiber with grid, tokens, terrain
- **Procedural World Generation** - Perlin noise terrain, biomes, structures
- **Quest System** - Multi-objective quests with progress tracking and rewards
- **Persistent SQLite Database** - WAL mode, characters, inventory, world state

### Advanced Features
- **DM Secrets System** - Hidden information with reveal conditions and spoiler formatting
- **Grand Strategy** - Nation management, diplomacy, fog of war, turn-based resolution
- **Multi-LLM Support** - Claude, GPT-4, Gemini, OpenRouter with tool calling
- **80+ MCP Tools** - Comprehensive API for all game mechanics

## 🚀 Quick Start

### Option 1: Desktop App

```bash
# Clone repositories
git clone https://github.com/Mnehmos/QuestKeeperAI-v2.git
git clone https://github.com/Mnehmos/rpg-mcp.git

# Build MCP backend
cd rpg-mcp
npm install
npm run build:binaries

# Copy binary to frontend (Windows example)
copy bin\rpg-mcp-win.exe ..\QuestKeeperAI-v2\src-tauri\binaries\rpg-mcp-server-x86_64-pc-windows-msvc.exe

# Run frontend
cd ../QuestKeeperAI-v2
npm install
npm run tauri dev
```

### Option 2: MCP Backend Only

```bash
# Clone and build
git clone https://github.com/Mnehmos/rpg-mcp.git
cd rpg-mcp
npm install
npm run build
```

Add to your MCP settings (Claude Desktop, RooCode, etc.):

```json
{
  "mcpServers": {
    "rpg-mcp": {
      "command": "node",
      "args": ["/path/to/rpg-mcp/dist/index.js"]
    }
  }
}
```

## 🎲 Example Session

```
You: Create a level 5 ranger named Lyra with high DEX and WIS

AI: [calls create_character tool]
    Created Lyra! Here's her character sheet:
    - Class: Ranger, Level 5
    - HP: 42/42, AC: 15
    - Stats: STR 12, DEX 18, CON 14, INT 10, WIS 16, CHA 10
    - Proficiencies: Survival, Stealth, Nature, Perception

You: Start combat with 3 goblins

AI: [calls create_encounter tool]
    ⚔️ Combat Initiated!
    
    Initiative Order:
    1. Lyra (18)
    2. Goblin Scout (15)
    3. Goblin Warrior (12)
    4. Goblin Archer (8)
    
    It's Lyra's turn! The goblins are 30 feet ahead.

You: Use Hunter's Mark on the scout and attack with my bow

AI: [calls dice_roll, execute_combat_action tools]
    Hunter's Mark cast (1st level slot consumed)
    Attack roll: 2d20kh1+7 = [18, 12] → 25 - HIT!
    Damage: 1d8+4 + 1d6 = 11 total
    
    The goblin scout falls! 2 enemies remain.
```

## 📚 Documentation

- **[Website](https://questkeeperai.com)** - Overview, features, and roadmap
- **[Quick Start](https://questkeeperai.com/quickstart)** - Setup instructions
- **[API Reference](https://questkeeperai.com/api-reference)** - All 80+ MCP tools documented
- **[System Analysis](https://questkeeperai.com/analysis)** - Architecture deep dive

## 🗺️ Roadmap

| Phase | Status | Features |
|-------|--------|----------|
| **Core Foundation** | ✅ Complete | Unified MCP server, Tauri app, characters, inventory, combat, quests, world gen |
| **Advanced Systems** | 🔄 In Progress | DM secrets, grand strategy, spatial combat, world map visualization |
| **Progression** | Upcoming | Skill system, quest chains, achievements, faction reputation |
| **Sessions** | Upcoming | Save/load, context condensing, campaign templates |
| **Platform** | Future | Universal RPG support, content marketplace, multiplayer |

## 🛠️ Tech Stack

**Frontend:**
- Tauri 2.x (Rust + Web)
- React 19 + TypeScript
- React Three Fiber / Three.js
- Zustand (state management)
- TailwindCSS

**Backend:**
- Node.js + TypeScript
- MCP SDK (Model Context Protocol)
- SQLite + better-sqlite3
- Zod (schema validation)
- pkg (binary bundling)

## 🔗 Links

- **Frontend Repo:** [github.com/Mnehmos/QuestKeeperAI-v2](https://github.com/Mnehmos/QuestKeeperAI-v2)
- **Backend Repo:** [github.com/Mnehmos/rpg-mcp](https://github.com/Mnehmos/rpg-mcp)
- **Website:** [questkeeperai.com](https://questkeeperai.com)
- **MCP Protocol:** [modelcontextprotocol.io](https://modelcontextprotocol.io)

## 📄 License

Apache License 2.0 - See [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments

- **D&D 5e SRD** - Core game mechanics
- **Anthropic** - Model Context Protocol
- **The TTRPG Community** - Inspiration and feedback

---

**Made with ⚔️ by solo developer | Powered by AI | Built for adventurers**
