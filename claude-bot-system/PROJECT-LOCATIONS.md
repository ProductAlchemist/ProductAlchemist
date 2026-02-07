# Project Locations Registry

**Purpose:** Central registry of all project paths across bots. Prevents path errors and enables cross-bot coordination.

**Last Updated:** Feb 7, 2026

---

## Primary Working Directory

```
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\
```

**Structure:** Parent Git repository (ProductAlchemist profile) containing submodules and projects

---

## Bot-Specific Projects

### Resume-Reviewer-Bot
**Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Resume-Reviewer-Bot`

**Structure:** Flat (6 files)
- 00-INDEX.md - Navigation guide
- 10-resume-master.md - 2-page comprehensive resume
- 11-resume-one-pager.md - 1-page condensed resume

**Entry Point:** Resume-Reviewer-Bot/00-INDEX.md

---

### Games-GitHub-Bot
**Primary Projects:**

**1. PlayLoop Studios Portfolio**
- **Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\playloop-studios`
- **Live URL:** https://playloop-studios.vercel.app/
- **GitHub:** https://github.com/ProductAlchemist/Playloop-Studios
- **Type:** Gaming portfolio (React + TypeScript + Firebase)
- **Games:** Tic-Tac-Toe, Snake, 2048
- **Deployment:** Vercel (auto-deploy from main branch)

**2. Cipher Daily Puzzle Game**
- **Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\Cipher`
- **Live URL:** https://cipher-daily.vercel.app
- **GitHub:** https://github.com/ProductAlchemist/cipher
- **Type:** Daily Wordle-style puzzle game (React + TypeScript + Firebase)
- **Firebase Link:** `cipher/youtubeLink` (controlled by YouTube bot)
- **Deployment:** Vercel (auto-deploy from main branch)

**3. Porter Case Studies**
- **Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\porter-case-studies`
- **GitHub:** https://github.com/ProductAlchemist/porter-case-studies
- **Type:** Product management case studies repository
- **Files:** lending-platform.md, taxation-system.md, partner-acquisition.md, acquisition-opportunity-sizing.md

**4. GitHub Profile**
- **Repository:** ProductAlchemist/ProductAlchemist (special profile README)
- **Location:** Parent directory README.md
- **Live URL:** https://github.com/ProductAlchemist

**Bot Directory:**
- **Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Games-GitHub-Bot`
- **Entry Point:** Games-GitHub-Bot/00-INDEX.md

---

### Interview-Prep-Bot
**Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Interview-Prep-Bot`

**Structure:** 3 folders (bot-context, user-reference, analysis)

**Entry Point:** Interview-Prep-Bot/CLAUDE.md (auto-loads when in bot dir)

**Post-Mortems:** Interview-Prep-Bot/analysis/[company]/

---

### YouTube-Automation-Bot
**Primary Project:**
- **Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\youtube-automation`
- **Production System:** `youtube-automation/production` (submodule)
- **Production Repo:** https://github.com/ProductAlchemist/youtube-puzzle-automation
- **Channel:** Puzzle Blitz (53 videos, 9 subscribers, ~20.8K views as of Feb 5, 2026)

**Entry Point:** youtube-automation/GETTING-STARTED.md or youtube-automation/CLAUDE.md

**Key Scripts:**
- `production/scripts/daily_workflow.py` - Upload automation
- `production/scripts/fetch_analytics.py` - Analytics fetching
- `production/scripts/ensure_auth.py` - Auth forcing function
- `production/scripts/pre_upload_validator.py` - Quality gates

**Firebase Integration:**
- `cipher/youtubeLink` - Controlled by YouTube bot (points to latest Cipher video)

---

## Cross-Bot Dependencies

### Cipher Game (Games + YouTube Coordination)

**Ownership:**
- **Games-GitHub-Bot owns:** Game code, deployment, Firebase game stats
- **YouTube-Automation-Bot owns:** Video creation, YouTube upload, Firebase `youtubeLink` field

**Workflow:**
1. Build game with Games-GitHub-Bot
2. Deploy to cipher-daily.vercel.app
3. Create videos featuring game with YouTube-Automation-Bot
4. YouTube bot updates Firebase link to latest video
5. Players click link in game → watch video → play game

**File References:**
- Game code: Cipher/ directory
- Video strategy: youtube-automation/11-MONETIZATION-STRATEGY.md
- Cross-bot guidance: CLAUDE.md (Bot Scope Decision Tree)

---

### Resume & Portfolio (Resume + Games Coordination)

**Ownership:**
- **Resume-Reviewer-Bot owns:** Resume content, bullets, tailoring
- **Games-GitHub-Bot owns:** Portfolio projects (playloop-studios, porter-case-studies)

**Workflow:**
1. Resume references portfolio projects
2. Games bot ensures portfolio is polished
3. Resume bot tailors bullets to highlight portfolio work
4. User sends resume + portfolio link to employers

**File References:**
- Resume: Resume-Reviewer-Bot/10-resume-master.md
- Portfolio: playloop-studios.vercel.app
- GitHub profile: https://github.com/ProductAlchemist

---

## AI Learning Projects

**AI-PM-Learning-Journey**
- **Location:** `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\AI-PM-Learning-Journey`
- **GitHub:** https://github.com/ProductAlchemist/AI-PM-Learning-Journey
- **Type:** Learning repository (Karpathy courses, LLM fundamentals)
- **Status:** Submodule in parent repo

---

## Development Environment Paths

**Python:**
- **Command:** `python` (NOT `py` or `py -3.11`)
- **Version:** Python 3.8.5
- **Location:** `C:\Users\Vivek Kulkarni\AppData\Local\Programs\Python\Python38-32\python`

**Node.js:**
- **Version:** v24.11.1
- **npm:** v11.6.2+

**Git:**
- **Version:** v2.52.0.windows.1
- **Bash:** Git Bash (for Claude Code compatibility)

**Claude Code:**
- **Version:** v2.0.50
- **Config:** `~/.claude/` (global) + `.claude/` (per-project)

**VS Code:**
- **Installed:** Yes (via winget)

---

## Temporary/Scratch Directories

**Claude Scratchpad (Session-Specific):**
```
C:\Users\Vivek Kulkarni\AppData\Local\Temp\claude\C--Users-Vivek-Kulkarni-Desktop-Playgroud-AI-Claude-Github-claude-bot-system\[session-id]\scratchpad
```

**Use for:** Temp files, intermediate results, working files during analysis

---

## Deprecated/Archive Locations

**Old Context Files (Pre-Cleanup):**
- youtube-automation/production had 50+ obsolete docs (cleaned Feb 2026)
- LEARNINGS.md, MISTAKES_AND_FIXES.md (moved to 11-PAST_MISTAKES_AND_FIXES.md)

---

## Path Conventions

**Absolute Paths Required:**
- All tool calls (Read, Write, Edit, Bash) require absolute paths
- Relative paths cause errors

**Windows Path Format:**
- Use backslashes `\` or forward slashes `/`
- Spaces in paths: Use quotes `"C:\Users\...\My Documents\"`

**Cross-Platform:**
- Git Bash uses Unix-style paths internally
- Windows Command Prompt uses Windows-style paths
- Claude Code normalizes automatically

---

## Quick Reference

```bash
# Navigate to bot directories:
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Resume-Reviewer-Bot"
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Games-GitHub-Bot"
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Interview-Prep-Bot"
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\youtube-automation"

# Navigate to project directories:
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\playloop-studios"
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\Cipher"
cd "C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\porter-case-studies"
```

---

## Maintenance

**Update this file when:**
- Adding new projects or repositories
- Moving/renaming directories
- Adding cross-bot dependencies
- Deprecating old locations
- Changing deployment URLs

**Last Major Update:** Feb 7, 2026 - Initial creation with all current projects
