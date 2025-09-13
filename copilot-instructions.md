# Copilot Instructions for VoiceAccess (voice.html)

## Project Overview
- **Single-file app**: All code (HTML, CSS, JS) is in `voice.html`.
- **Purpose**: Voice-controlled accessibility dashboard for web, with features for voice navigation, accessibility toggles, and keyboard shortcuts.
- **Architecture**: The app is a client-side SPA (Single Page Application) managed by the `VoiceAccessibilityApp` class. No backend or build system is present.

## Key Components & Patterns
- **Navigation**: Sidebar and header navigation switch visible pages by toggling `.page` elements. Use `navigateToPage(page)` for programmatic navigation.
- **Settings**: All user settings (e.g., high contrast, large text, voice commands) are managed in the `settings` object and toggled via UI or voice/keyboard commands.
- **Voice Control**: Uses Web Speech API (`SpeechRecognition`, `speechSynthesis`) for voice commands and feedback. Voice commands are processed in `processVoiceCommand()`.
- **Accessibility**: High-contrast and large-text modes are toggled by adding classes to `<body>`. ARIA roles and keyboard navigation are enhanced on DOMContentLoaded.
- **Keyboard Shortcuts**: See the Shortcuts page in the UI for all bindings. Example: `Ctrl+Shift+V` toggles voice control, `Alt+Shift+H` toggles high contrast.
- **PWA Support**: Registers a service worker at runtime for offline caching, but all assets are inlined in `voice.html`.

## Developer Workflows
- **No build step**: Edit `voice.html` directly. No external dependencies or package managers.
- **Testing**: Manual testing in a browser is required. Grant microphone access to test voice features.
- **Debugging**: Use browser dev tools. Console logs are present for settings, performance, and errors.
- **Persistence**: Settings are not persisted (see `saveSettings`/`loadSettings` stubs).

## Project-Specific Conventions
- **All logic is in one file**: Keep new features in `voice.html`.
- **Class-based app structure**: Extend or modify `VoiceAccessibilityApp` for new features.
- **UI state**: Controlled by toggling classes and updating DOM directly.
- **No external libraries**: All code is vanilla JS/CSS/HTML.

## Examples
- To add a new accessibility toggle: Add a toggle in the HTML, update `settings`, and handle it in `updateUI()` and `setupToggleListeners()`.
- To add a new voice command: Extend `processVoiceCommand()` with new phrase logic.

## Key File
- `voice.html`: The entire application (UI, logic, styles, and service worker registration).

---

**If you add new files or external dependencies, update this document.**
