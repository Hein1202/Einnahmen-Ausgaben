# Einnahmen-Ausgaben (Offline) – Version 179.03.26

Dieses Projekt ist die aktuelle Electron-/EXE-Basis für das kombinierte Programm **Einnahmen + Ausgaben**.
Die EXE-/Electron-Version ist die maßgebliche Hauptversion. Dieselben HTML-Dateien können zusätzlich in GitHub / im Browser verwendet werden.

## Funktionen
- Einnahmen erfassen und monatsweise verwalten
- Ausgaben erfassen und monatsweise verwalten
- Jahresübersicht anzeigen
- Excel-Export offline
- JSON-Speichern / JSON-Import
- Druckfunktionen für Monats- und Quartalsausgaben

## Projektstruktur
- `index.html` – Startseite / Navigation / sichtige Versionsanzeige
- `einnahmen.html` – Einnahmen-Modul
- `ausgaben.html` – Ausgaben-Modul
- `jahresuebersicht.html` – Jahresübersicht
- `electron/main.js` – Electron-Hauptprozess
- `electron/preload.js` – Bridge für Dateispeichern in der EXE
- `assets/xlsx.full.min.js` – Excel-Export (SheetJS)
- `assets/tailwind.css` – Styles / Fallback
- `build/icon.ico` – Programmsymbol

## Starten (Entwicklung)
1. Node.js (LTS) installieren
2. In diesem Ordner im Terminal ausführen:
   - `npm install`
   - `npm start`

## EXE bauen (Windows)
- `npm run dist`
- Die Ausgabe liegt danach im Ordner `dist/`

## Hinweise zur Versionsnummer
Die sichtige Versionsnummer wird in `index.html` angezeigt.
Wenn sich die Versionsnummer ändert und du die GitHub-Version aktualisieren willst, musst du immer **`index.html` plus die geänderte Programmdatei** hochladen.

## Aktueller Stand dieser Version
- Version auf **179.03.26** erhöht
- README überarbeitet und erweitert
- Ausgaben: **„Datei speichern“** in der EXE auf die vorhandene Electron-Speicherfunktion umgestellt
