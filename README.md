# Quest Keeper AI

**The first AI-powered tabletop RPG platform with full D&D 5e mechanics, spatial combat, and universal system support.**

![Status](https://img.shields.io/badge/status-alpha-yellow)
![License](https://img.shields.io/badge/license-Apache%202.0-blue)
![MCP Tools](https://img.shields.io/badge/MCP%20tools-97-brightgreen)

## 🎮 Play Now in Alpha

Quest Keeper AI is **playable now** in alpha state through third-party AI code assistants that support MCP (Model Context Protocol):

- **[Claude Desktop](https://claude.ai/download)** - Official Anthropic desktop app with native MCP support
- **[KiloCode.ai](https://kilocode.ai)** - AI-powered coding assistant with MCP support
- **[RooCode.com](https://roocode.com)** - Full-featured AI development environment

📖 **[Quick Start Guide](https://questkeeperai.com/quickstart)** - Get started in minutes

## 🚀 Overview

Quest Keeper AI transforms AI assistants into powerful Dungeon Masters using the Model Context Protocol (MCP). The system provides:

- **Full D&D 5e Mechanics** - Complete implementation of combat, spells, abilities, and character progression
- **3D Spatial Combat** - Tactical battlefield with line-of-sight, cover, flanking, and elevation
- **Persistent World State** - SQLite-backed game state that survives across sessions
- **97 MCP Tools** - Comprehensive API for AI-driven gameplay across two specialized servers
- **Stronghold Management** - Domain-level play with base building, hirelings, and passive income
- **Universal System Ready** - Extensible architecture for Pathfinder, Call of Cthulhu, and custom systems

## 🏗️ Architecture

Quest Keeper uses a dual-server architecture:

### Game State Server (68 tools)
- Character & NPC management
- Inventory & equipment
- World state persistence
- Encounter & combat tracking
- Quest system
- Spell management with slot tracking
- Stronghold & domain management
- Batch operations for performance

### Combat Engine Server (29 tools)
- Dice rolling with advantage/disadvantage
- D&D 5e attack & damage calculations
- 3D spatial battlefield system
- Line-of-sight & area-of-effect targeting
- Tactical analysis & positioning
- ASCII battlefield visualization
- Legendary & lair actions

## 📚 Documentation

- **[Comprehensive Analysis](https://questkeeperai.com/analysis)** - 18,000-word deep dive into architecture and features
- **[API Reference](https://questkeeperai.com/api-reference)** - Complete documentation for all 97 MCP tools
- **[Implementation Roadmap](https://questkeeperai.com/roadmap)** - Development path from alpha to multiplayer platform
- **[Quick Start Guide](https://questkeeperai.com/quickstart)** - Setup instructions for all compatible platforms

## 🎯 Key Features

### Immersive AI Dungeon Master
- Natural language interaction with full D&D 5e rules enforcement
- Dynamic narrative generation based on player choices
- Intelligent NPC behavior and dialogue
- Automated combat calculations and turn management

### Advanced Combat System
- 3D tactical battlefield with terrain and obstacles
- Real-time line-of-sight calculations
- Flanking, cover, and height advantage mechanics
- ASCII battlefield maps with fog of war
- Support for legendary actions and lair actions

### Persistent Campaign Management
- SQLite database for reliable state persistence
- Character progression tracking
- Quest and story arc management
- World state that evolves based on player actions
- Multiple characters per campaign

### Stronghold & Domain Play
- Build and upgrade facilities (barracks, libraries, workshops)
- Recruit and manage hirelings
- Generate passive income from businesses
- Respond to dynamic stronghold events
- Domain-level strategic gameplay

## 🚀 Quick Start

### Prerequisites
- Node.js 16+
- Git
- One of the compatible AI platforms (Claude Desktop, KiloCode, or RooCode)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Mnehmos/rpg-mcp-servers.git
   cd rpg-mcp-servers
   ```

2. **Install and build both servers**
   ```bash
   # Game State Server
   cd game-state-server
   npm install && npm run build

   # Combat Engine Server
   cd ../combat-engine-server
   npm install && npm run build
   ```

3. **Configure MCP settings**

   Add to your MCP settings file (location varies by platform):

   ```json
   {
     "mcpServers": {
       "rpg-game-state": {
         "command": "node",
         "args": ["/path/to/rpg-mcp-servers/game-state-server/build/index.js"],
         "alwaysAllow": ["*"]
       },
       "rpg-combat-engine": {
         "command": "node",
         "args": ["/path/to/rpg-mcp-servers/combat-engine-server/build/index.js"],
         "alwaysAllow": ["*"]
       }
     }
   }
   ```

4. **Start playing!**

   Open your AI assistant and start with:
   ```
   Create a level 5 ranger named Lyra with high DEX and WIS
   ```

See the **[Quick Start Guide](https://questkeeperai.com/quickstart)** for detailed setup instructions.

## 🎲 Example Gameplay

```
DM: You stand at the entrance to the Goblin Caves. The air is thick with
    the smell of smoke and unwashed bodies. What do you do?

Player: I ready my bow and move cautiously into the cave

DM: [rolls Stealth check with your +7 modifier]
    You rolled 18 - success! You move silently into the darkness.

    Suddenly, three goblins spot you from behind cover!
    [rolls initiative for all combatants]

    Initiative Order:
    1. Goblin Scout (17)
    2. Lyra (15) ← YOUR TURN
    3. Goblin Warrior (12)
    4. Goblin Archer (8)

    The goblin scout is 30 feet ahead behind a barrel.
    Two more goblins are 40 feet away near some crates.

    What do you do?

Player: I use Hunter's Mark on the scout and shoot him with advantage

DM: [casts Hunter's Mark, consuming a 1st level spell slot]
    [rolls attack with advantage: 2d20kh1+7]
    You rolled [18, 12] → 18 + 7 = 25 - HIT!

    [rolls damage: 1d8+4 (longbow) + 1d6 (Hunter's Mark)]
    Damage: 7 piercing + 4 force = 11 total damage

    Your arrow finds its mark! The goblin scout clutches his chest
    and falls backward, dead. The other goblins shriek in rage!
```

## 🛠️ Technology Stack

- **Language**: TypeScript 4.9+
- **Runtime**: Node.js 16+
- **Database**: SQLite 3
- **Protocol**: Model Context Protocol (MCP) v1.12.3+
- **Game System**: D&D 5e SRD

## 🗺️ Development Roadmap

### Phase 1: Foundation (Current - Alpha)
- ✅ Core D&D 5e mechanics
- ✅ Dual-server architecture
- ✅ Spatial combat engine
- ✅ Stronghold system
- 🔄 API stability improvements
- 🔄 Testing & bug fixes

### Phase 2: Universal Systems
- Rules engine abstraction
- Pathfinder 2e support
- Call of Cthulhu support
- Custom system builder

### Phase 3: Multiplayer Foundation
- Real-time session sharing
- Party management
- DM controls and permissions
- Spectator mode

### Phase 4: Platform Launch
- Web-based interface
- Mobile apps
- Matchmaking system
- Community features

### Phase 5: Visual Integration (Post-Launch)
- Video generation system
- Character visualizations
- Scene rendering
- Animation system

See the **[Implementation Roadmap](https://questkeeperai.com/roadmap)** for full details.

## 🤝 Contributing

Contributions are welcome! This is a solo-developed project in alpha stage.

### Ways to Contribute
- 🐛 Report bugs and issues
- 💡 Suggest features and improvements
- 📖 Improve documentation
- 🧪 Write tests
- 🔧 Submit pull requests

### Development Setup
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Test thoroughly
5. Commit: `git commit -m 'Add amazing feature'`
6. Push: `git push origin feature/amazing-feature`
7. Open a Pull Request

## 📊 Project Stats

- **97 MCP Tools** across two servers
- **~10,000 lines** of TypeScript
- **Full D&D 5e** combat mechanics
- **3D spatial** battlefield system
- **Stronghold management** with 19 tools
- **Quest tracking** system
- **Spell management** with slot tracking

## 🔗 Links

- **Website**: [https://questkeeperai.com](https://questkeeperai.com)
- **MCP Servers Repository**: [https://github.com/Mnehmos/rpg-mcp-servers](https://github.com/Mnehmos/rpg-mcp-servers)
- **Documentation**: [https://questkeeperai.com](https://questkeeperai.com)
- **Model Context Protocol**: [https://modelcontextprotocol.io/](https://modelcontextprotocol.io/)

## 📄 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **D&D 5e System Reference Document** - Core game mechanics
- **Anthropic** - Model Context Protocol specification
- **Claude 4.5 Sonnet** - Analysis and documentation generation
- **The TTRPG Community** - Inspiration and feedback

## 📞 Contact

Questions? Feedback? Found a bug?

- **Issues**: [GitHub Issues](https://github.com/Mnehmos/quest-keeper-ai/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Mnehmos/quest-keeper-ai/discussions)

---

**Made with ⚔️ by solo developer | Powered by AI | Built for the community**
