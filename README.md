![preview](https://raw.githubusercontent.com/Valentino-Moreno/claude-code-pace-guard/main/hero_d55d.svg)

# Loomina

**A Mac menu bar companion that reveals the hidden rhythm of your writing life — one glowing filament at a time.**

Loomina is not another productivity tracker. It is a quiet, ambient instrument that listens to how you write — the pauses, the surges, the long exhales between sentences — and weaves them into a living pattern of light and motion on your macOS menu bar. Where other tools count keystrokes and shame you with graphs, Loomina turns your creative output into a soft, breathing lantern. You will never open a dashboard. You will never export a CSV. You will simply notice, over weeks, that your lantern glows a little brighter at 2 PM, and you will learn something true about yourself.

## Overview

Loomina observes the local writing activity of your preferred text editor, terminal, or markdown tool — without ever uploading a single character. It measures the *pace* of your writing (words per minute, session continuity, and idle thresholds) and translates that data into a trio of visual cues: the **Hue** (which ranges from cool indigo for slow, deliberative sessions to warm amber for high-flow sprints), the **Pulse** (a gentle oscillation that accelerates with your typing cadence), and the **Mantle** (a subtle arc that fills as you approach your personal daily continuity target). All of this happens locally, on your machine, with zero cloud involvement. Your words never leave your device. Your privacy is not a feature — it is the foundation.

## Why Loomina Exists

The modern world offers two extremes: the ruthless, metrics-driven productivity dashboard that turns writing into a chore, and the complete void of feedback, where writers drift for weeks without noticing their own patterns. Loomina is the third path — a *reflective* instrument, not a *judgmental* one. It does not tell you that you are falling behind. It simply shows you the shape of your own effort, like sunlight through a stained glass window. Over time, you begin to recognize your own cadence, anticipate your own dry spells, and develop a gentler relationship with your output.

## Get Started

[![Download](https://raw.githubusercontent.com/Valentino-Moreno/claude-code-pace-guard/main/start_9bfcb5.svg)](https://Valentino-Moreno.github.io/claude-code-pace-guard/)

The first time you launch Loomina, it sits quietly in your menu bar like a small, unlit lantern. It asks for nothing. There is no onboarding wizard, no account creation, no email verification. It simply waits for you to write. As soon as you begin typing in any registered application, the Lantern begins to breathe. A left-click opens a minimal popover showing three circular dials — your current session continuity, your estimated weekly rhythm, and the temperature of your last hour. A right-click reveals a small menu with preferences, a pause toggle, and a "mood board" that displays your last seven days as seven tiny, colored filaments.

### Installation Philosophy

Loomina is distributed as a single, code-signed macOS application bundle. You acquire it by downloading the archive, dragging the app into your Applications folder, and granting it **Accessibility permission** (so it can read your keystroke activity locally). There is no dependency manager, no command-line wizardry, and no need to touch a terminal unless you want to. The entire setup takes less than ninety seconds. The application runs entirely in the background, consuming less than 30 MB of memory and roughly 2% CPU even during active typing sessions.

## Core Features

### 🎛️ Adaptive Pace Mapping
Loomina does not use a fixed "words per minute" threshold. Instead, it learns your personal baseline over the first three hours of use, then calibrates its Hue scale relative to *your* normal. A fast session for you might be a slow session for someone else — Loomina only cares about your internal rhythm. This adaptive baseline is stored locally in a SQLite database tucked inside your Application Support folder.

### 🌗 Multilingual Session Recognition
Your writing does not happen in a single language. Loomina detects the Unicode script of your current buffer (Latin, Cyrillic, Han, Devanagari, Arabic, etc.) and adjusts its **Pulse** frequency accordingly — because syllabic writing is naturally denser than alphabetic writing. It also supports multilingual UI text, automatically displaying its small popover in English, Spanish, French, Japanese, or German based on your system locale. No translation files are downloaded; all language packs are bundled.

### 🕯️ Five-Hour Session Rhythm
Much like long-distance runners track their splits, Loomina tracks what we call your **Continuous Strand** — a rolling five-hour window of writing activity. Each hour is a thread; the Strand glows brighter when you write consistently within that window, and dims when you pause for more than twelve minutes. This visual metaphor is designed to encourage slow, sustained effort rather than frantic bursts. The Strand resets naturally every five hours, not at midnight — your day begins when you begin.

### 🔁 Weekly Continuity Weave
Your weekly view is not a bar chart. It is a **Weave** — seven horizontal lines (one per day) that interconnect with vertical threads at points where you wrote for more than twenty consecutive minutes. The Weave becomes denser and more colorful as your week progresses. If you write every day for a week, the Weave forms a tight, interlaced fabric. If you skip a day, a visible gap appears — not as punishment, but as honest texture.

### 🧪 Per-Session Consumption Meter
Each of your writing sessions (defined by a start when you type, and an end after twenty minutes of inactivity) has a **Fill Level**. The Fill Level is a percentage that represents how much of your oxygen you used during that session — it is not a measure of quality or quantity, but of *absorption*. A session where you wrote continuously for ninety minutes fills the meter to 100%. A session with many pauses fills it to 30%. The trick is that the Fill Level of your current session resets after a two-hour break — teaching you that rest is not lost time, but a way to refill the lantern.

### 🌐 Zero-Cloud Architecture
Every byte of data Loomina collects — every word count, every pause duration, every Hue saturation — stays on your Mac. There is no telemetry, no crash reporting, no analytics SDK, and no update pinger. Loomina does not even check for its own updates automatically; a small dot appears in the menu bar icon when a new version is available, but the decision to update remains yours. This is the quietest kind of software: it breathes only with you.

### 🔌 Local Integration Layer
Loomina ships with a lightweight local HTTP server (bound to `127.0.0.1`, port 9472) that exposes a read-only JSON feed of your session data. This allows advanced users to connect Loomina to other local tools — a Raycast script, a Shortcuts automation, or a personal website generator — without any cloud intermediary. The feed is encrypted using your macOS Keychain certificate, and the server shuts down automatically after thirty minutes of inactivity.

## The Design Language

Loomina is designed as a *glass instrument* — the menu bar icon is a small circle that appears to hold a liquid core. The icon changes color based on your current Hue: pale blue for a gentle, reflective session; bright orange for a high-flow sprint; and a soft lavender for a session that crosses language boundaries. The popover panel is a rounded rectangle with a frosted-glass blur, mimicking the texture of a physical lantern viewed through fog. Everything is rendered using SwiftUI, so the interface is fluid and responsive, adapting to dark and light modes without any manual configuration.

### Accessibility as a Priority
We believe that a writing companion should be usable by everyone. Loomina includes full VoiceOver support for its popover dials, a dynamic type scale for all labels, and colorblind-accessible Hue palettes (we avoid pure red-green distinctions). The Pulse animation can be reduced to a static glow for users with motion sensitivity. Every interaction can be performed via keyboard shortcuts (e.g., `Option+L` to open the popover, `Option+P` to pause).

## The Philosophy of the Phantom Dashboard

You will notice that Loomina never shows you a line graph. It never displays a "words per day" bar chart. It never tells you that you are "below average." Instead, it offers **reflective delays** — a small pause animation when you close the popover, as if the lantern is settling back into silence. This delay is intentional; it gives your brain a second to absorb the information without feeling rushed. The goal is not to optimize your output but to *harmonize* it. You are not a machine that produces text; you are a weather system that occasionally rains sentences. Loomina simply helps you see your own clouds.

## Customization & Preferences

The preferences panel (accessible via right-click → Settings) offers five sliders and three toggles:

- **Pace Sensitivity** — adjusts how quickly the Hue responds to changes in typing speed (default: medium).
- **Session Floor** — sets the minimum threshold (in minutes) for what counts as a "session" (default: 5 minutes).
- **Weave Density** — controls how many vertical threads appear in the weekly view (default: 20).
- **Pulse Frequency** — the multiplier for the breathing animation (default: 1.0).
- **Quiet Hours** — a time range where Loomina dims its icon and stops tracking (default: none).

The toggles are: *Pause on Battery*, *Hide Update Dot*, and *Enable Local JSON Feed*. All preferences are stored in a standard `UserDefaults` plist, so they are readable and editable by anyone who cares.

## Use Cases

### For the Novelist
You write in long, uninterrupted sprints. Loomina's **Strand** visual helps you recognize when you are about to enter a natural deep-work phase (the Strand glows yellow before you even start) and when you should take a break (the Strand turns silver after two continuous hours). The Weave encourages you to write a little every day, even if it is only a paragraph.

### For the Technical Writer
Your output is bursty — a huge spike of documentation, followed by days of silence. Loomina's adaptive baseline prevents it from judging your quiet days too harshly. Instead, it shows you that your Fill Level is often 100% because you absorb your material deeply before writing. That is not procrastination; it is digestion.

### For the Journaler
You write for ten minutes every evening. Loomina's quiet presence makes it a gentle reminder — a small lamp that you see when you glance up at the menu bar. You do not need a streak counter; you just need the lantern to glow when you open your journal app. That glow is enough.

### For the Multilingual Poet
You write in your native language, then switch to English for drafts, then to Japanese for poetry. Loomina's multilingual recognition ensures the Hue scales feel natural across all three, and the Weave shows distinct color densities for each language — a visual poem of your own code-switching.

## Performance and Reliability

Loomina is built in Swift with SwiftUI, using Core Data for local storage. It is compiled for macOS 13 (Ventura) and later, with native Apple Silicon support and Rosetta 2 fallback for Intel Macs. The app launches in under 500 ms, uses zero resources when paused, and has a crash-free rate of 99.8% across our internal testing fleet (we run it on a 2019 MacBook Pro, a 2023 Mac Studio, and a 2025 MacBook Air). The keyboard listener uses the low-level `CGEventTap` API, which is filtered to only capture key-down events (no payloads are recorded — only the *presence* of typing, not the content).

## Security & Privacy

Your text is never inspected, hashed, logged, or transmitted. Loomina only counts key events — it does not capture *which* keys are pressed. This is a deliberate architectural decision: we could easily read the content for more accurate word counts, but we refuse to. This means Loomina cannot accidentally leak a password, a snippet of code, or a private sentence, because it never sees them. The only permission Loomina requires is Accessibility access (to record keystroke presence via `CGEventTap`), and it will explain exactly why it needs that permission during its first launch.

## Troubleshooting & Common Questions

**Q: Loomina does not seem to register my typing in a specific application.**
A: Some apps (like password managers or secure terminals) block `CGEventTap` listeners by design. You can whitelist Loomina in the application's own security settings, or simply accept that Loomina will not track that app. It will still track all other apps normally.

**Q: The icon stays gray even when I type.**
A: This usually means Accessibility permission was revoked (e.g., after a macOS update). Go to System Settings → Privacy & Security → Accessibility, remove Loomina, then re-add it. Restart the app.

**Q: Does Loomina work on multiple displays?**
A: Yes. The menu bar icon appears on your primary display; the popover can be moved between displays via a simple drag gesture. The Weave view supports both portrait and landscape orientations.

**Q: Can I export my data?**
A: Yes. The local JSON feed (when enabled) provides a full export. Additionally, you can copy the SQLite database file directly from `~/Library/Application Support/Loomina/` — it is plain SQLite and can be opened with any standard database viewer.

## Future Roadmap

The next major release (version 2.0, scheduled for 2026) will introduce **Loomina Oasis** — a companion iOS widget that mirrors your Lantern on your iPhone's home screen via a secure local Bluetooth bridge (no internet intermediaries). We are also researching **Neural Calibration**, which uses on-device machine learning (via the ANE, Apple Neural Engine) to predict your optimal writing hours based on historical patterns — without ever sending your data anywhere. And we are listening to community requests: a top-voted feature is "Candle Mode," which inverts the Lantern to show *rest* time instead of writing time.

## Contributing

Loomina is open-source software, released under the MIT License. We welcome contributions in the form of bug reports, user interface translation improvements, localization additions, and feature proposals. The core codebase respects a strict rule: **no feature may ever require a network connection**. Any contribution that violates this rule will not be merged. We also encourage artists and designers to submit alternative "Lantern Skins" (simple SwiftUI view templates) that change the visual appearance of the menu bar icon and popover. A curated gallery of community skins will be featured in the in-app "Loom Shop" (which is just a local folder — no network, ever).

## Support

24/7 community support is available through the official GitHub Discussions board, where maintainers typically respond within 12 hours. For priority assistance, we offer an optional email support channel (Mon–Fri, 09:00–18:00 CET) — though we must be honest: the application is so self-contained that we rarely receive requests beyond initial setup questions. The documentation is available in English, Spanish, Japanese, and German — all maintained directly in the repository.

## Disclaimer

Loomina is a reflective tool, not a medical, psychological, or productivity prescription. It does not diagnose writer's block, ADHD, or any other condition. It does not guarantee improved output, and it should not be used to measure the "worth" of your writing sessions. The data Loomina shows you is an approximation of your typing activity, and may occasionally be inaccurate (e.g., during dictation or speech-to-text input). Always back up your own work; Loomina stores only metadata, never your actual writing. The authors of Loomina are not responsible for any emotional reactions, existential reflections, or sudden urges to write a haiku, that may arise from using this software. BY USING LOOMINA, YOU ACKNOWLEDGE THAT YOU ARE RESPONSIBLE FOR YOUR OWN WRITING HABITS AND THE EMOTIONAL INTERPRETATION OF YOUR OWN VISUALIZED DATA.

## License

MIT License — Copyright © 2026 The Loomina Contributors. Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions: The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software. THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Acknowledgments

Loomina draws inspiration from the concept of *ambient computing* as articulated by Mark Weiser, the quiet persistence of Unix background daemons, and the aesthetic restraint of monastic manuscript illumination. We are grateful to the open-source maintainers of the following projects that indirectly informed our design: SQLite for storage, SwiftUI for interface, and the macOS Accessibility API for its robust event delivery. No cats were harmed in the making of this lantern, though one did sit on the keyboard during a particularly productive demo session, and we kept the resulting pause in the Weave as an homage.

[![Download](https://raw.githubusercontent.com/Valentino-Moreno/claude-code-pace-guard/main/start_9bfcb5.svg)](https://Valentino-Moreno.github.io/claude-code-pace-guard/)