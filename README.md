# Cadence — Speak English with Confidence

AI-powered English communication training. Built for adults who want to sound less translated and more native.

## Features

- **Live speech transcription** with Web Speech API
- **Voice synthesis** using your system's native English voices
- **YouTube import**: paste any video link + transcript to practice shadowing
- **Real-time analysis**: filler detection, calque detection, WPM, fluency score
- **8 modules**: Today, Speak, Shadow, Conversations, Content Feed, Vocabulary, Library, My Patterns
- **Dark/Light mode** with persistence
- **Mobile-optimized** with touch targets, safe-area insets, hamburger nav
- **Keyboard shortcuts**: 1-8 to switch views, Space to record in Speak, Esc to cancel

## Tech

Pure HTML + CSS + JS. No build step. Web Speech API for STT and TTS. Canvas for waveform visualization. LocalStorage for persistence.

Compatible: Chrome, Edge, Safari (desktop and mobile). Firefox supports TTS but not live transcription.

## Deploy

This is a static site. Just deploy `index.html`.
