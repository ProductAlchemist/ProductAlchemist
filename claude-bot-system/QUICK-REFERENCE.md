# Quick Reference Card

**Last Updated:** Feb 7, 2026

---

## ⚠️ Critical Commands (Forcing Functions)

### Python (NEVER use `py`)
```bash
# ✅ ALWAYS use:
python script.py
python -m pip install package

# ❌ NEVER use (triggers Windows Store):
py script.py
py -3.11 script.py
python3 script.py
```

**Why:** User frustration Feb 7, 2026: "I can't keep repeating the same things over & over"

**Manual fix for PowerShell** (optional):
```powershell
# Run this ONCE in PowerShell:
if (!(Test-Path -Path $PROFILE)) { New-Item -ItemType File -Path $PROFILE -Force }
Add-Content -Path $PROFILE -Value "`nSet-Alias -Name py -Value python"
```

---

## Claude Code Session Commands

### Starting Sessions (Session Hygiene)

```bash
# Resume Bot: Start fresh session
cd Resume-Reviewer-Bot && claude

# Games Bot: Start fresh session
cd Games-GitHub-Bot && claude

# Interview Bot: Start fresh session
cd Interview-Prep-Bot && claude

# YouTube Bot: Start fresh session
cd youtube-automation && claude
```

**Why separate sessions?**
- Prevents context bloat
- No auto-compaction needed
- Clean mental separation
- CLAUDE.md auto-loads per bot

### Continuing Work (Same Bot)

```bash
# Continue SAME work on SAME bot:
claude -c

# Pick conversation for project:
claude -r
```

**When to use `claude -c`:**
- ONLY for continuing same work on same bot
- NOT for switching between bots (start fresh instead)

---

## Git Workflow

### Pre-Commit Checklist

```bash
# 1. Check status + diff + log (parallel):
git status
git diff HEAD
git log --oneline -5

# 2. Stage specific files (NOT git add -A):
git add file1.md file2.py

# 3. Commit with Co-Authored-By:
git commit -m "$(cat <<'EOF'
Your commit message here

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>
EOF
)"

# 4. Push (RISKY - confirm first):
git push
```

**Safety Rules:**
- ❌ Never `git add -A` (can include secrets, temp files)
- ❌ Never force push to main/master without user approval
- ❌ Never skip hooks with `--no-verify`
- ✅ Add specific files by name
- ✅ Verify with `git status` after commit

---

## YouTube Automation (Production System)

### Daily Upload Workflow

```bash
cd youtube-automation/production

# Upload specific puzzles:
python daily_workflow.py 90 96 105

# Force regenerate videos (if stale):
python daily_workflow.py 90 96 --force-regen

# Fetch analytics:
python fetch_analytics.py --all-test-videos --checkpoint 24h
```

**MANDATORY GATES (Never Bypass):**
- Gate 0a: Pre-upload validation (quality checks)
- Gate 0b: Test data detection (blocks TEST, PLACEHOLDER keywords)
- Manual video review before confirming upload

**YouTube API = Source of Truth:**
```bash
# ✅ ALWAYS query API for channel data:
# channels().list(mine=True) for stats
# playlistItems().list() for video list

# ❌ NEVER trust local files:
# youtube_videos_full.json (stale cache)
# video_upload_tracker.json (stale cache)
```

**Before ANY Research:**
1. Read `production/Analysis/CHANNEL-INTELLIGENCE.md` FIRST
2. If question already answered → Use it, don't re-research
3. If new question → Research, then ADD to CHANNEL-INTELLIGENCE.md

---

## Bot-Specific Entry Points

### Resume-Reviewer-Bot
**Entry:** `Resume-Reviewer-Bot/00-INDEX.md`

**Always Load:**
- 10-resume-master.md (2-page resume)
- 11-resume-one-pager.md (1-page resume)
- 11-PAST_MISTAKES_AND_FIXES.md (resume-specific learnings)

**Selective Load:**
- 20-context.md (only if complex narrative needed - 352KB)

---

### Games-GitHub-Bot
**Entry:** `Games-GitHub-Bot/00-INDEX.md`

**Always Load (MANDATORY):**
- 10-MANDATORY-PROCESS.md (process checklist)
- 11-PAST_MISTAKES_AND_FIXES.md (prevents catastrophic errors)

**Selective Load:**
- 20-github-projects.md (for project work)
- 21-GAME_INTEGRATION_CHECKLIST.md (for game integration)
- 30-context.md (only if deep history needed - 1.4MB)

**Projects:**
- playloop-studios: `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\playloop-studios`
- cipher: `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\Cipher`
- porter-case-studies: `C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\porter-case-studies`

---

### Interview-Prep-Bot
**Entry:** `Interview-Prep-Bot/CLAUDE.md` (auto-loads)

**Always Load:**
- 11-PAST_MISTAKES_AND_FIXES.md (interview-specific learnings)

**Structure:**
- bot-context/ (Claude's knowledge: fintech fundamentals, company research)
- user-reference/ (User refers: prep checklist, memorized answers)
- analysis/ (Post-mortems per company)

---

### YouTube-Automation-Bot
**Entry:** `youtube-automation/GETTING-STARTED.md` or `youtube-automation/CLAUDE.md`

**Always Load:**
- 11-PAST_MISTAKES_AND_FIXES.md (YouTube-specific learnings + blocking gates)

**Critical Files:**
- PRE_UPLOAD_CHECKLIST.md (quality verification)
- production/Analysis/CHANNEL-INTELLIGENCE.md (settled knowledge from 7 research rounds)

---

## File Operations (Use Dedicated Tools)

```bash
# ❌ DON'T use Bash for these:
cat file.txt          # Use Read tool instead
grep "pattern" *.md   # Use Grep tool instead
find . -name "*.py"   # Use Glob tool instead
echo "text" > file    # Use Write tool instead
sed 's/old/new/' file # Use Edit tool instead

# ✅ DO use Bash for:
git status
npm install
python script.py
pytest tests/
docker build
```

**Why:** Dedicated tools allow better user review and understanding

---

## Verification Before Completion

```bash
# ✅ "Completed" means VERIFIED complete:

# Verify files exist/deleted:
find . -name "filename"
ls -la path/

# Verify content changed:
cat file | grep "expected"

# Verify no old references:
grep -r "old-pattern" .

# ❌ "Should be complete" is NOT verified
```

---

## Path Quick Copy

```bash
# Bot directories:
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Resume-Reviewer-Bot
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Games-GitHub-Bot
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\Interview-Prep-Bot
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\claude-bot-system\youtube-automation

# Project directories:
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\playloop-studios
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\Cipher
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github\porter-case-studies

# Parent directory:
C:\Users\Vivek Kulkarni\Desktop\Playgroud\AI\Claude\Github
```

---

## Scratchpad (Temp Files)

**Session-specific temp directory:**
```
C:\Users\Vivek Kulkarni\AppData\Local\Temp\claude\C--Users-Vivek-Kulkarni-Desktop-Playgroud-AI-Claude-Github-claude-bot-system\[session-id]\scratchpad
```

**Use for:**
- Intermediate results during multi-step tasks
- Temporary scripts or config files
- Analysis outputs that don't belong in project

**DON'T use `/tmp` unless explicitly requested**

---

## Error Prevention Shortcuts

### Before Proposing Solution:
```
✅ Check tool --help first
✅ Search PAST_MISTAKES: grep -i "keyword" [BOT]/11-PAST_MISTAKES_AND_FIXES.md
✅ Clarify requirement with user
✅ Show checklist work in response
```

### Before Destructive Operations:
```
✅ Read current state first
✅ Verify impact scope
✅ Ask for confirmation (pushing, deleting, force operations)
```

### Bot Boundary Respect:
```
✅ Changes to bot IA: Ask per-bot, don't batch all 4
✅ Root system changes: Mention impact on each bot
```

---

## User Communication Style

**Expects:**
- Direct, concise responses
- Anti-confirmation bias (challenge assumptions)
- Verification, not assurances
- Structured thinking with checklist work shown
- Forcing functions, not documentation

**Rejects:**
- Verbose explanations
- Validation over honesty
- Claims without proof
- Repeated mistakes
- Band-aid fixes

**Key Quote:**
> "Get out of confirmation bias, challenge me when you want to"

---

## Token Management

### Session Hygiene (Best Practice)
- One bot per session (prevents context bloat)
- Exit when done, start fresh for next bot
- CLAUDE.md auto-loads (context preserved)

### Manual Compaction (If Needed)
```bash
# Check token usage mid-session:
/context

# Proactive compaction at 70% usage:
/compact

# DON'T wait for auto-compact (more expensive)
```

---

## Last Resort (When Stuck)

### Read the Docs
1. Check `[BOT]/11-PAST_MISTAKES_AND_FIXES.md` for similar issue
2. Check `CLAUDE.md` for rules and processes
3. Check `ARCHITECTURE.md` for system design
4. Check `IA-GAPS.md` for known weaknesses

### User Standards
- "Someone somewhere has solved this" - research before guessing
- Expects industry best practices, not "best I can think of"
- Applied: Poka-Yoke (manufacturing) + DevOps guardrails + AI agent reliability

---

**Remember:** This is a quick reference, not a replacement for reading the full documentation. When in doubt, consult the full CLAUDE.md and bot-specific files.
