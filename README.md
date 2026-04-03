# Einnahmen-Ausgaben (Offline)

Dieses Projekt ist die neue, saubere Electron/EXE-Basis für das kombinierte Programm **Einnahmen + Ausgaben**.

## Starten (Entwicklung)
1. Node.js (LTS) installieren
2. In diesem Ordner:
   - `npm install`
   - `npm start`

## EXE bauen (Windows)
- `npm run dist`
- Output liegt danach im Ordner `dist/`

## Excel-Export
Die Datei **assets/xlsx.full.min.js** ist bereits enthalten (SheetJS Standalone), damit der Excel-Export offline funktioniert.

## Dateien
- `index.html` – App (Version 234.04.26)
- `electron/main.js` – Electron Main
- `electron/preload.js` – API Bridge (`window.electronAPI.saveBinaryFile`)
- `assets/` – externe Assets (xlsx)

## Versionsnummer
Die App-Version wird in `index.html` angezeigt und ist aktuell: **234.04.26**
