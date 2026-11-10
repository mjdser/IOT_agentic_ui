# IOT Agentic UI

**Majd Sarahni** and **Aseel Fraira**

Describe a screen in plain language. The tool writes the LVGL interface and its tests, flashes them to an ESP32, and runs the tests on the real display. A camera photographs the screen, a second model checks the photos, and failures go back to the writer to fix.

This project is part of [ICST](https://icst.cs.technion.ac.il/), the Interdisciplinary Center for Smart Technologies at the Taub Faculty of Computer Science, Technion.

## What is in this repo

- `tools/ui_generator` — chat page and the generator that writes, flashes, and checks the UI
- `lvgl_ui` — the generated interface and the on-device test hooks
- `ESP32` — firmware
- `flutter_app` — the Flutter app
- `test` — on-device tests for the display and the touch panel
- `Documentation` — wiring notes

## Hardware

ESP32 (DOIT DevKit v1), an ILI9341 display, and an XPT2046 touch panel.

## Run the generator

Copy `.env.example` to `.env` and set `GEMINI_API_KEY`. Do not commit `.env`.

```
python tools/ui_generator/server.py
```

Then open http://127.0.0.1:8765

Setup, the camera, and the test loop are documented in `tools/ui_generator/README.md`.
