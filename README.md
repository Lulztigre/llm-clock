# ⚡ LLM Radar Clock CLI & Terminal Plugin v2.5

> **Live Peak Hours Surge Tracker, Vector Radar Reticle & Off-Peak Discount Telemetry**  
> Pure Python 3.9+ zero-dependency vector radar clock, Tmux plugin, Starship module, and workload gatekeeper for **Z.ai GLM-5.3**, **DeepSeek V4.1-Flash & V4-Pro-0813**, **Qwen / Qoder**, **MiniMax**, and **Moonshot / Kimi** APIs.

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat&logo=python&logoColor=white)](https://python.org)
[![Platform](https://img.shields.io/badge/Platform-Linux%20|%20macOS%20|%20Windows-brightgreen?style=flat)]()
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero%20(Pure%20Stdlib)-blue)]()
[![License](https://img.shields.io/badge/License-MIT-purple)]()

🌐 **Live Web Version:** [lulztigre.pw/llm-clock.html](https://lulztigre.pw/llm-clock.html)  
📦 **Repository:** [github.com/lulztigre/llm-clock](https://github.com/lulztigre/llm-clock)

---

## 🛰️ Overview

The **LLM Radar Clock** tracks real-time peak surge vs. off-peak discount windows across major AI foundation models and coding platforms based on official Beijing (UTC+8 / CST) & UTC surge schedules.

| AI Model / Provider | Peak Surge Window (Mon-Fri) | Peak Rate | Off-Peak Rate | Weekend Policy |
| :--- | :--- | :--- | :--- | :--- |
| **GLM-5.3 / GLM-5-Turbo** | `14:00 - 18:00 UTC+8` | **3.0× Quota Surge** | **1.0× Standard** | 100% Off-Peak All Day |
| **DeepSeek V4.1-Flash & V4-Pro-0813** | `09:00 - 12:00` & `14:00 - 18:00 UTC+8` | **2.0× Surge** | **1.0× (50% Discount)** | 100% Off-Peak All Day |
| **Qwen / Qoder (Qwen-Coder & Max)** | `08:00 - 22:00 UTC+8` *(14:00-00:00 UTC Off-Peak)* | **2.0× Standard** | **1.0× (50-80% Disc.)** | 100% Off-Peak All Day |
| **MiniMax-01 / Babble-Pro** | `10:00 - 12:00` & `15:00 - 18:00 UTC+8` | **1.5× Surge** | **1.0× Standard** | 100% Off-Peak All Day |
| **Moonshot / Kimi K1.5 & K2** | `09:30 - 11:30` & `14:30 - 17:30 UTC+8` | **2.0× Surge** | **1.0× Standard** | 100% Off-Peak All Day |

---

## ⚡ Quick Installation

### Option 1: Instant Single-Line Run *(No installation needed)*

**Linux & macOS:**
```bash
curl -sSL https://raw.githubusercontent.com/lulztigre/llm-clock/main/llm_clock.py | python3
```

**Windows (PowerShell / Windows Terminal):**
```powershell
irm https://raw.githubusercontent.com/lulztigre/llm-clock/main/llm_clock.py | python
```

---

### Option 2: Install as CLI tool via pip / pipx

```bash
# Global pip install directly from GitHub
pip install git+https://github.com/lulztigre/llm-clock.git

# Or with pipx (isolated Python environment)
pipx install git+https://github.com/lulztigre/llm-clock.git
```

Then run anywhere:
```bash
llm-clock
```

---

### Option 3: Download Standalone Script

```bash
# Linux / macOS
curl -O https://raw.githubusercontent.com/lulztigre/llm-clock/main/llm_clock.py
chmod +x llm_clock.py
./llm_clock.py

# Windows PowerShell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/lulztigre/llm-clock/main/llm_clock.py" -OutFile "llm_clock.py"
python llm_clock.py
```

---

## 🖥️ Interactive Radar TUI Features

Launch the interactive high-definition Unicode Braille vector radar display:
```bash
llm-clock
# Or specify provider
llm-clock -p qoder
```

```
┌─ LLM_CLOCK // TACTICAL TELEMETRY RADAR v2.5 ──────────────────────────────────────────────────┐
│                                      │  PROVIDER:   Qwen / Qoder (Qwen-Coder & 3.8-Max)          │
│             ⢀⣀⠤⠤⠒⠒⠖⠒⠲⠤⢤⣀             │  STATUS:     [STATE: PEAK_SURGE // 2.0X COEFFICIENT]      │
│          ⢀⡤⠊⠉           ⠙⠲⢄          │  RATE COEFFICIENT: 2.0× SURGE RATE                        │
│        ⢀⠔⠉           ⡜   ⢀⠔⠑⣄        │  COUNTDOWN:  06h 15m 00s (Off-Peak Discount)              │
│       ⢠⠋      ⢀⡠⠤⠤⠤⠤⡼⣀ ⢀⠔⠁  ⠈⢳⣶⡀     │  BEIJING (UTC+8): 2026-08-28 15:45:00 CST                 │
│      ⢠⠇     ⢀⠔⠉    ⢠⠃⢈⠕⢅      ⢻⣷     │  WORKSTATION:    2026-08-28 08:45:00 Local                │
│      ⡞     ⢀⠏     ⢀⢇⠔⠁ ⠈⢇     ⠘⣿⡆    │  SURGE WINDOWS:  08:00-22:00 UTC+8 (00:00-14:00 UTC)      │
│      ⡇⠠   ⣀⣸⣀⣀⣀⡠⠤⠤⣾⠥⠒⠒⠒⠊⢹⠁   ⠠ ⣿⡇    │  DIAL / THEME:   12H Reticle │ VOID PHOSPHOR              │
│      ⣇ ⠉⠉⠉ ⠘⡄           ⡜     ⢀⣿⡇    │  ────────────────────────────────────────────             │
│      ⠸⡄     ⠙⢄        ⢀⠜⠁     ⣸⣿     │  Peak rate active. Credit consumption at standard rate.   │
│       ⠱⡀      ⠙⠢⠤⠤⠤⠤⠤⠚⠁      ⣰⣿⠃     │  [P]rov [M]ode [T]heme [SPC]Hold [←→↑↓]Scrub [K]alc [Q]   │
│        ⠙⢄                  ⢀⣾⡿⠃      │                                                           │
│          ⠙⠦⡀            ⢀⣠⣴⡿⠋        │                                                           │
│            ⠈⠙⠒⠤⠤⣀⣀⣄⣀⣠⣤⣴⣶⠿⠛⠉          │                                                           │
│                   ⠛⠛⠛⠉⠉              │                                                           │
├─ GLOBAL METROPOLIS SURGE MATRIX (LIVE TIMEZONE CONVERSION) ───────────────────────────────────┤
│  [CN/SG] Beijing / Singapor 15:45 PEAK (2.0X) │  [JP/KR] Tokyo / Seoul      16:45 PEAK (2.0X) │
│  [UK/EU] London (UTC+0/1)   08:45 PEAK (2.0X) │  [EU] Paris / Berlin     09:45 PEAK (2.0X)    │
│  [US-E] New York (EDT)     03:45 PEAK (2.0X)  │  [US-W] San Francisco (PDT 00:45 PEAK (2.0X)  │
│  [IN] Bengaluru (IST)    13:15 PEAK (2.0X)    │  [AU] Sydney (AEST)      17:45 PEAK (2.0X)    │
└───────────────────────────────────────────────────────────────────────────────────────────────┘
```

### 🎮 Keyboard Controls

- `p` : Cycle AI Providers (`GLM` ➔ `DeepSeek` ➔ `Qwen/Qoder` ➔ `MiniMax` ➔ `Kimi`)
- `m` : Toggle Reticle Mode (`12-Hour` ⟷ `24-Hour` Reticle)
- `t` : Cycle Visual Themes (`Void Green`, `CRT Amber`, `Bloodmoon`, `Arctic`, `Synthwave`, `Matrix`)
- `Space` : **HOLD Mode** (freeze time to inspect radar dial)
- `←` / `→` or `↑` / `↓` : **Time-Travel Scrubber** (scrub ±1s/±1m in HOLD mode or ±15m/±1h live)
- `r` : Reset time scrubber back to real-time clock
- `k` : **Interactive Token / Cost Calculator**
- `q` : Exit

---

## 🛑 Workload Gatekeeper (`--wait-offpeak`)

Block automated scripts, agent sweeper loops, and CI/CD jobs until the off-peak discount window opens:

```bash
# Block until off-peak discount is active, then execute heavy agent workflow
llm-clock --provider qoder --wait-offpeak && python run_swe_bench.py
```

Outputs a live countdown spinner and chime before exiting with return code 0:
```
⚡ [GATEKEEPER] Monitoring Qwen / Qoder Peak Hours Surge...
⠋ PEAK SURGE ACTIVE (2.0x) ⏳ Off-peak resumes in: 06h 14m 20s
```

---

## 📊 Multi-Provider Matrix View

Compare the live status of all major LLM providers simultaneously:

```bash
llm-clock -p all
```

Output:
```
┌─ LLM_CLOCK // MULTI-PROVIDER PRICING MATRIX ────────────────────────┐
│  BEIJING CST: 2026-08-28 15:45:00 (UTC+8)                             │
├────────────────────────┬─────────────┬────────────┬─────────────────┤
│  MODEL / PROVIDER      │  STATE      │  RATE      │  NEXT PHASE     │
├────────────────────────┼─────────────┼────────────┼─────────────────┤
│  GLM                   │  PEAK SURGE │  3.0×      │  02h 15m 00s    │
│  DeepSeek              │  PEAK SURGE │  2.0×      │  02h 15m 00s    │
│  Qwen/Qoder            │  PEAK SURGE │  2.0×      │  06h 15m 00s    │
│  MiniMax               │  PEAK SURGE │  1.5×      │  02h 15m 00s    │
│  Kimi                  │  PEAK SURGE │  2.0×      │  01h 45m 00s    │
└────────────────────────┴─────────────┴────────────┴─────────────────┘
```

---

## 🧩 Statusline & Prompt Plugins

### 🟢 Tmux (`~/.tmux.conf`)
```tmux
set -g status-right '#(llm-clock --provider qoder --format tmux) | %H:%M '
set -g status-interval 15
```

### 🚀 Starship Prompt (`~/.config/starship.toml`)
```toml
[custom.llm_clock]
command = "llm-clock --provider qoder --format starship"
when = "true"
format = "[$output]($style) "
```

### 💻 Zsh / Bash Prompt (`.zshrc` / `.bashrc`)
```bash
# Add live surge badge to right prompt
RPROMPT='$(llm-clock --provider qoder --format prompt)'

# Quick CLI alias
alias llm='llm-clock --format short'
```

### 🪟 Windows PowerShell (`$PROFILE`)
```powershell
function prompt {
    $status = llm-clock --provider qoder --format short
    "$status PS $($executionContext.SessionState.Path.CurrentLocation)> "
}
```

### 📊 Waybar / Polybar / i3blocks (`JSON IPC Mode`)
```json
{
  "exec": "llm-clock --provider qoder --format waybar",
  "return-type": "json",
  "interval": 30
}
```

---

## 📄 License

MIT License © 2026 [LulzTigre](https://lulztigre.pw)
