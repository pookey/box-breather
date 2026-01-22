# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Box Breather is a minimal, distraction-free box breathing timer. It's a single-file web app (`index.html`) with no build process or dependencies.

## Running the App

Open `index.html` directly in a browser. No server required.

## Architecture

Everything is in one file with embedded CSS and JS:

- **Phases array** (line ~200): Defines the 4-phase breathing cycle (inhale → hold → exhale → hold) with start/end coordinates for the chaser
- **Animation loop** (`animate` function): Uses `requestAnimationFrame` and `performance.now()` to calculate phase progress based on wall-clock time
- **Background brightness**: Tied to phase index (0=inhale brightens, 1=hold bright, 2=exhale darkens, 3=hold dark)
- **Click sounds**: Web Audio API oscillator generates ticks at phase transitions - no external audio files

## Key Settings

- Phase duration: 3-6 seconds (applies to each of the 4 phases)
- Brightness pulse intensity: Controls how bright the screen gets during inhale/hold
- Click volume: 0-100% for phase transition sounds
