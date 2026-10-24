# LocalFlow

LocalFlow is a Windows desktop dictation and meeting transcription app. It captures speech locally, transcribes it with selectable speech models, and can refine text before inserting it into the active application. The project also includes a browser companion extension for meeting speaker information.

**Devin Hack Kochi code repository:** [KarthikSambhuR/DevinHacksKochi](https://github.com/KarthikSambhuR/DevinHacksKochi)

## Project overview

- **Project name:** LocalFlow
- **Short description:** Offline-first Windows dictation and meeting transcription with local speech and text models.
- **Team:** TODO — add participant names and GitHub handles.
- **Working demo:** TODO — add a demo link or local walkthrough.
- **Technology stack:** Go, Wails, JavaScript, Whisper.cpp, ONNX Runtime, SQLite, and a Manifest V3 browser extension.

## Features

- Global hotkey dictation with a compact overlay and local transcription.
- Optional text refinement and vocabulary personalization.
- Meeting transcription and summaries using locally configured models.
- Browser companion extension support for meeting speaker names.
- Local transcript storage and cleanup controls.

Model availability and performance depend on the model files and hardware configured on the user's machine. The browser companion requires manual installation in a supported browser.

## Run from source

### Prerequisites

- Windows 10 or later.
- Go 1.25 or later, as specified in `go.mod`.
- Node.js and npm for the Wails frontend.
- Wails v2 CLI (the module uses v2.10.2).
- A C compiler and CGO-enabled Go toolchain for native dependencies.

### Setup and development

```powershell
git clone https://github.com/KarthikSambhuR/DevinHacksKochi.git
cd DevinHacksKochi
cd frontend
npm ci
cd ..
go install github.com/wailsapp/wails/v2/cmd/wails@v2.10.2
wails dev
```

The application may need model files downloaded through its model settings before transcription features are available. Do not commit private model files, API keys, or local transcript data.

### Checks

```powershell
cd frontend
npm ci
npm run build
cd ..
go test ./...
node --test extension/bridge.test.cjs
```

Run checks from the repository root unless the command says otherwise. Record the actual result in `CHANGELOG.md` when making a change.

## Libraries and data sources

- [Wails](https://wails.io/) provides the Go desktop application shell and webview integration.
- [whisper.cpp](https://github.com/ggml-org/whisper.cpp) provides speech recognition components.
- [ONNX Runtime](https://onnxruntime.ai/) runs supported local inference models.
- [modernc SQLite](https://pkg.go.dev/modernc.org/sqlite) provides local database storage.
- Other Go dependencies and versions are listed in `go.mod`; frontend dependencies are listed in `frontend/package.json` and its lockfile.
- No public dataset is bundled with the project. Speech and text inference use locally configured model files.

## Current status

- Working features: dictation, transcript management, meeting transcription, model settings, and browser companion integration are implemented in the repository.
- Known limitations: Windows is the supported desktop target; model downloads and browser companion setup are separate user steps. Meeting-platform selectors and speaker attribution still need live validation. The app records mixed microphone/system audio rather than isolated speaker tracks, and the local browser bridge has no pairing token; do not expose its port.
- Validation results: see the latest project entry in `CHANGELOG.md`.

See [MEETING_AUDIT.md](MEETING_AUDIT.md) for the detailed limitations and live-call checklist. Read [RULES.md](RULES.md) for event guidance, [AGENTS.md](AGENTS.md) for repository workflow, [AI_USAGE.md](AI_USAGE.md) for the actual AI assistance record, and [SUBMISSION.md](SUBMISSION.md) for submission details.
