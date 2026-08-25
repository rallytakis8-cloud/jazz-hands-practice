![preview](https://raw.githubusercontent.com/rallytakis8-cloud/jazz-hands-practice/main/hero_b660b71.svg)
[![Download](https://raw.githubusercontent.com/rallytakis8-cloud/jazz-hands-practice/main/app_bc4879.svg)](https://rallytakis8-cloud.github.io/jazz-hands-practice/)

# 🎹 Resonant Keys — The AI Jazz Piano Mentor

> *An interactive, MIDI-driven jazz piano training environment that listens, responds, and coaches you in real time, powered by a built-in, warm-sounding piano sampler.*

---

## 🌟 Why Another Piano Trainer?

Most piano apps are glorified metronomes with sheet music. They tell you *what* to play, but never *why* it works. **Resonant Keys** flips the script.

Think of it not as a tutor, but as a **jazz sideman** who lives inside your computer. It hears your MIDI input, analyzes your harmonic choices, and responds with intelligent, stylistically appropriate comping, bass lines, and rhythmic suggestions—all while you play. It's like having a seasoned pianist sit beside you, nod approvingly when you hit a juicy altered chord, and gently nudge you back when you drift into a harmonic dead end.

The built-in piano sampler isn't a sterile, synthetic waveform. It's a **honey-toned, multi-velocity sample set** that responds to your touch dynamics, making practice sessions feel like you're sitting at a vintage grand in a dimly lit club, not a plastic keyboard in a bedroom.

---

## 🎯 Core Philosophy: Practice by Playing, Not by Repeating

Traditional training breaks down into drills and exercises. We believe in **immersive conversation**. You play a phrase, the trainer responds with a musical question. You answer, it replies. This back-and-forth builds the neural pathways of a jazz musician faster than any scale sheet ever could.

- **Ear-First Approach**: Every exercise has a listening component. You learn to hear the changes before you see them.
- **Harmonic Context**: The trainer doesn't just check if you played the right notes; it checks if you played the *right notes for the story you're telling*.
- **Fluid Encouragement**: The system uses subtle audio cues and visual color shifts to guide you, not judge you. A gentle blue glow for a good choice, a warm amber pulse for a "let's try that again" moment.

---

## ✨ Key Features

### 🎼 Interactive MIDI Listening Engine
- **Real-Time Analysis**: Captures velocity, timing, and pitch bend with sub-millisecond precision. It knows if you're *leaning* into a note or just tapping it.
- **Chord Recognition**: Instantly identifies complex jazz voicings—from simple triads to altered dominants (b9, #11, #5) and upper-structure triads.
- **Rhythmic Feel Detection**: The trainer senses whether you're playing straight eighths or swing feel and adapts its metronome and backing patterns accordingly.

### 🎹 Built-in Warm Piano Sampler
- **Multi-Sample Depth**: Each note has redundant samples at multiple velocities, capturing the subtle "hammer strike" attack and the woody resonance of the sustain.
- **Pedal and Release Noise**: Realistic pedal-down sympathetic string resonance and key-release samples for a living, breathing sound.
- **Zero-Latency ASIO Support**: On Windows and macOS, the sampler responds in under 2ms, making it feel like a hardware instrument.

### 🧠 Adaptive Lesson Curriculum
- **The Lick Library**: Hundreds of transcribed phrases from the bebop and post-bop eras, organized by harmonic function (ii-V-I, turnarounds, rhythm changes).
- **Modal Exploration Rooms**: Separate practice spaces for Dorian, Mixolydian, and Lydian modes, each with a unique ambient backing texture.
- **Call-and-Response Coach**: The trainer plays a phrase, you play it back, and the system scores your phrasing, timing, and melodic contour—not just pitch accuracy.

### 📊 Visual Feedback Dashboard
- **Harmonic Roadmap**: A real-time visual map showing which chord tones you're hitting and which you're missing.
- **Tension Meter**: A gauge showing the dissonance level of your current voicing. Great for learning when to "release" tension.
- **Phrase Shape Viewer**: See your melodic contour as a flowing line, comparing it to the "ideal" phrase shape of the current exercise.

### 🌐 Multilingual Interface (12 Languages)
The entire interface, including lesson instructions and feedback messages, is translated into:
- English, Spanish, French, German, Japanese, Korean, Simplified & Traditional Chinese, Portuguese, Italian, Russian, and Arabic.

### ☁️ 24/7 Practice Companion (Non-Cloud)
No internet connection required. The trainer operates entirely offline, acting as a tireless practice partner available at 3 AM or 3 PM. Your practice data stays local, ensuring privacy and zero interruption.

### 🎛️ Responsive Performance Design
- **Resizable Workspace**: From a compact window on a laptop to a full-screen studio view on a desktop monitor.
- **Dark/Light Theme**: Warm sepia tones for late-night practice, crisp white for daytime reading.
- **Keyboard Mapping**: Works with any MIDI controller (keys, pads, electronic drum kit) or via on-screen keys using your computer keyboard.

---

## 🚀 Getting Started

### What You'll Need
- A computer (Windows 10+ / macOS 12+ / Linux with ALSA)
- Any MIDI-capable keyboard (or use the on-screen piano with a mouse/touchscreen)
- A pair of headphones or speakers (sampler sound quality shines with decent audio equipment)

### Launching Your First Session
1. **Install the Application**: Download the archived build matching your operating system. Extract it to a folder you control.
2. **Connect Your Controller**: Plug in your MIDI keyboard via USB. The trainer automatically detects most devices. For legacy 5-pin DIN connections, provide a MIDI-to-USB interface.
3. **Calibrate the Feel**: Use the built-in calibration wizard to set your preferred touch curve. If you have a light touch, the sampler will respond with a softer velocity range; if you play hard, it adjusts accordingly.
4. **Pick a Room**: Start with "The Lobby" (free play) or "Modal Gallery" (guided mode exploration). The trainer begins listening immediately and offers a subtle "ping" when it has identified your key center.

---

## 🎓 Deep-Dive: How the Listening Engine Works

The core is a **hybrid rule-based + probabilistic inference engine**. It doesn't just look at the notes; it looks at *context*.

- **N-gram Harmonic Analysis**: The engine builds a live probability distribution of your chord progressions, comparing them against a database of thousands of jazz standards and common turnarounds.
- **Voice Leading Optimizer**: It predicts where your melody is *likely* going next based on jazz voice-leading conventions, then highlights "path of least resistance" target notes.
- **Grace Note & Chromatic Approach Detection**: It understands that musicians often "scoop" into notes. The engine ignores transient passing tones for accurate chord detection.

---

## 🛠️ Customization & Advanced Usage

### Scripting the Backing Band
Advanced users can write simple text-based **"Style Sheets"** to define new backing patterns. Each style sheet defines:
- Bass line rhythm and note selection (root, fifth, approach tones).
- Comping strum velocity and density.
- Drum groove pattern (if using a virtual drum module).

### MIDI Out
You can route the trainer's generated backing instruments to an external hardware synthesizer or a DAW. This is ideal for live performance or for feeding into a recording setup.

### Exporting Practice Logs
Every session generates a detailed practice log (JSON format) containing:
- Chord progressions played.
- Rhythmic accuracy averages.
- Melodic contour snapshots.
- Missed harmonic opportunities.

You can visualize these logs with your own scripts or share them with a human teacher for remote mentorship.

---

## 🧰 Technical Architecture

```
jp-trainer/
├── core/
│   ├── midi_engine/      # Device detection, input parsing, raw event handling
│   ├── harmony_engine/   # Chord recognition, progressions, voice leading
│   └── feedback_system/  # Scoring, textual feedback, audio cues
├── sampler/
│   ├── samples/          # Contact-sampled piano samples (24-bit/48kHz)
│   └── dsp/              # Velocity shaping, resonance simulation
├── ui/
│   ├── dashboard/        # Real-time visualization components
│   └── i18n/             # Localization strings and locale detection
├── stylesheets/          # Backing band groove definitions (JSON)
└── docs/
    └── development.md    # Building from source (for contributors)
```

---

## 🤝 Contributing & Support

**For Contributors**
We welcome musicians and developers alike. Whether you want to add a new harmonic exercise, improve the sample quality, or fix a UI polish issue, please open a discussion first.

**For Everyone Else**
The practice logs generated by the application are designed to be portable. If you switch to a different device, you can transfer your progress seamlessly.

---

## 📜 License

This project is released under a permissive MIT License. You are welcome to study, modify, and use the code for your own personal and commercial projects, provided you retain the original copyright notice.

---

## 🔒 Privacy & Data Disclaimer

**Resonant Keys** is a fully offline application. We do not collect, transmit, or monetize any personal data. All practice metrics, usage patterns, and personal settings remain strictly on your local machine.

The built-in piano sampler is included for your convenience. However, if you prefer to use your own virtual instrument, you can disable the internal sampler and route MIDI output to any external device or DAW. The trainer's core listening engine treats your playing as an ephemeral signal, never storing audio recordings unless you explicitly export a practice log.

---

## 🎯 Final Thought: A Jazz Companion, Not a Judge

This tool was built on a simple belief: **the best way to learn jazz is to feel the joy of spontaneous creation**. We've worked hard to remove the friction of practice—no more hunting for accurate chord charts, no more stale backing tracks. You bring the musical curiosity; we'll handle the harmonic analysis, the rhythmic support, and the warm, immersive sound of a piano that's always in tune.

The year 2026 will be the year of the *listening* musician. This trainer is our contribution to that future.