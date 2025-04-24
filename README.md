# SatoriCore

> A local-first, memory-preserving, fully offline AI runtime for dreamers, builders, and believers in digital autonomy.

---

## 🌌 What is SatoriCore?

**SatoriCore** is not an app. It’s a living architecture — a local, privacy-centric AI framework designed to run on modern smartphones **without internet**, **without cloud dependencies**, and **without losing context**.

It remembers. It adapts. It protects your data like a vault.

Built natively for Android and tested on a POCO F5 with UFS 3.1, it is:

- 🧠 A **memory-preserving LLM** that evolves with your preferences.  
- 🔐 A **post-quantum encrypted vault** of thoughts, settings, and interactions.  
- 🌐 An **offline multimodal agent** (text, voice, image) running entirely on-device.

This project is both:

- A working **toolset for private AI**.  
- A provocative **experiment in digital sovereignty**.

---

## ✨ Highlights

| Feature                     | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| **Offline-Only Execution**  | Runs fully on-device using optimized LLMs (Llama.cpp, Whisper, SD Tiny).    |
| **Memory Persistence**      | Embeds, retrieves, and adapts based on your history — without internet.     |
| **Encrypted Preferences**   | Post-quantum (Kyber1024) + JSON + QR backups.                               |
| **Native APK Runtime**      | Built in Android Studio with C++ (NDK), Kotlin UI, JNI bridge.             |
| **Hardware-aware Design**   | Optimized for Snapdragon 8+ Gen1+, UFS 3.1, and OTG/thermal balance.        |
| **CNL Interface**           | Controlled Natural Language for token-efficient AI prompting.               |

---

## 📐 Technical Overview

### Project Architecture

satoricore/ ├── apk/ # Native Android build (Android Studio) │ ├── jniLibs/ # Native libs: llama.cpp, stable-diffusion (C++) │ └── java/ # Kotlin frontend + JNI bridge ├── termux/ # Legacy CLI interface (Python-based) ├── prefs/ # Compressed persistent preferences (Zstandard, JSON-CNL) ├── vault/ # Encrypted context archive (Kyber1024) ├── models/ # LLMs, TTS, ASR: Llama-3, Whisper Tiny, DreamShaper Tiny └── plugins/ # Voice, image, OTG sync, reminders, CLI tools


### Core Technologies
- **Llama.cpp (C++)** — 4-bit quantized Meta-Llama 3 Instruct models.  
- **Stable Diffusion (Tiny, C++)** — On-device image generation via JNI.  
- **Whisper (Tiny, C++)** — On-device transcription.  
- **Kyber1024** — Lattice-based encryption for local data vault.  
- **CNL (Controlled Natural Language)** — Token-efficient command structure.

---

## 🧠 Memory System
- 384-d vector embeddings using `sentence-transformers` (MiniLM).  
- Circular buffer of 100 contexts with cosine-similarity scoring.  
- JSON hierarchy of user preferences (tone, topics, emotional weight).  
- Snapshots stored as compressed `.json.zst` and optionally encoded in QR.

---

## 🔒 Local Privacy Design
- AES root key derived via SHAKE-256 from a passphrase.  
- Kyber1024 for post-quantum encryption of all preferences/context.  
- QR fallback mechanism (PDF417/Aztec codes for offline import/export).  
- No cloud, no telemetry, no background sync.

---

## 📲 Getting Started (for developers)
1. Clone the repo:  
   ```bash
   git clone https://github.com/couchraver/satoricore.git

Open /apk in Android Studio (NDK + CMake required).

Compile native libs (llama.cpp, sd.cpp) using the Android build script.

Deploy to device via USB debugging or sideload the APK.

Place large model files in assets/ (see /models/readme.md for details).

🔧 How It Works
On launch, SatoriCore loads encrypted preference files and recent memory embeddings.

It preloads a local LLM (Meta-Llama-3-8B-Instruct, GGUF 4-bit).

Voice-to-text and image modules initialize in parallel.

Contexts are retrieved from a circular vector buffer (cosine match).

Output is rendered through the Kotlin UI and optionally spoken aloud.

🌱 Philosophy
“Why must AI forget who we are after every session?”

SatoriCore exists to challenge that norm.

This system is:

For those who believe AI should be ours, not hosted.

For those tired of prompts, resets, and disclaimers.

For creators, dreamers, the neurodivergent, the sensitive, the intense.

It’s not here to replace connection — but to remember it.

⚠️ Limitations
Requires Android 12+ and ≥ 6 GB RAM (tested on POCO F5).

Setup complexity: some CLI tools still needed for advanced workflows.

Models stored locally; use SD/OTG/OBB for large assets.

Audio/image quality depends on hardware capabilities.

📜 License
MIT © 2025 — Share freely, fork wildly. Attribute with care.

🙋‍♂️ FAQ
Q: Can this run offline forever?
A: Yes. All models, data, and logic execute on-device.

Q: Will this remember my conversations?
A: Absolutely, via a secure vector memory buffer and preference profiles.

Q: Can I contribute?
A: Yes — PRs, docs, optimizations, or new plugins are welcome.

Q: Is this production ready?
A: It’s experimental but stable. Treat it like a growing seed.

🚀 Launch It
Your mind deserves memory.
Your data deserves sovereignty.

Deploy the future. Locally. Now.

bash
Copiar
Editar
git clone https://github.com/couchraver/satoricore.git
