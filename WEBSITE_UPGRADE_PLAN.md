# Implementation Plan - Website & Documentation Upgrade

The goal is to propagate the aesthetic (Glassmorphism, Animations) and content upgrades (135+ Tools, Spellcasting, Economy) across the entire Quest Keeper AI website suite.

## User Review Required

> [!IMPORTANT]
> The "API Reference" page typically lists all tools. Manually updating this list to 135+ tools might be verbose. I will focus on updating the **Categories** and **Summary** sections unless you want a full list regeneration (which requires the raw tool list).

- **Current Status**: `index.html` is 90% complete (minor list fixes needed).
- **Target Pages**: `analysis`, `roadmap`, `api-reference`, `quickstart`, `style-guide`.

## Proposed Changes

### 1. Global Styles (`styles.css`)

- [x] Already updated with `gradientMove`, `.reveal`, glassmorphism classes.
- [ ] **Verify**: Ensure all sub-pages correctly link to this stylesheet and using the shared classes.

### 2. Landing Page (`index.html`) - Finalization

- [ ] **Fix**: Update `server-features` list (Spellcasting, Economy, Corpse).
- [ ] **Fix**: Update Comparison table (Roll20/D&D Beyond tool counts).

### 3. Documentation Pages Updates

#### A. Analysis (`analysis/index.html`)

- [ ] **Aesthetics**: Apply `reveal` animation classes to sections.
- [ ] **Content**:
  - Update architecture diagrams/text to mention **135+ Tools**.
  - Mention new sub-systems: **Spellcasting**, **Theft/Economy**, **Corpse/Loot**.

#### B. Roadmap (`roadmap/index.html`)

- [ ] **Aesthetics**: Apply `reveal` classes.
- [ ] **Content**:
  - Mark **Phase 2 (Advanced Systems)** items as ✅ Complete:
    - Spellcasting
    - Theft & Economy
    - Corpse & Loot
    - NPC Memory
  - Update **Phase 3** with new stretch goals if applicable.

#### C. API Reference (`api-reference/index.html`)

- [ ] **Aesthetics**: Glassmorphism for tool category cards.
- [ ] **Content**:
  - Update intro text (80+ -> 135+).
  - Add new Categories: **Spellcasting**, **Theft**, **Corpse**, **NPC Memory**, **Improvisation**.
  - _Note_: If this page contains a table of all tools, I will update the summary but ideally, this should be generated from `RPG-MCP-TOOL-METADATA.md`.

#### D. Quick Start (`quickstart/index.html`)

- [ ] **Aesthetics**: Glassmorphism for code blocks and steps.
- [ ] **Content**:
  - Ensure binary names/links match the latest release info.
  - Mention the new capabilities users can test immediately.

#### E. Style Guide (`style-guide/index.html`)

- [ ] **Aesthetics**: Ensure the guide itself uses the new Design System it describes.
- [ ] **Content**: Add documentation for the new `.reveal` animations and `.glass-card` utilities.

## Verification

- [ ] Use `browser_subagent` to visually verify `index.html` and one sub-page (e.g., `roadmap/index.html`) to ensure CSS paths are correct.
- [ ] Commit and Push changes for live preview.
