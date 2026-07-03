# AR Model Viewer & Direct Downloader

Ein leichtgewichtiges, HTML/JavaScript-basiertes System, um 3D-Modelle (`.glb`) über die Cloud zu teilen, direkt auf Endgeräte herunterzuladen oder sofort im Web-Browser in Augmented Reality (AR) zu betrachten. 

Das Projekt nutzt die **Litterbox API (catbox.moe)** für den temporären Datei-Upload (24 Stunden Gültigkeit) und Googles `<model-viewer>` für die AR-Darstellung.

---

## System-Architektur

Das System besteht aus zwei eigenständigen HTML-Seiten:

1. **`viewer.html` (AR Model Viewer)**
   * Das Haupt-Dashboard. Erlaubt den Drag-and-Drop / Datei-Upload von `.glb`-Dateien.
   * Lädt die Datei hoch, generiert einen QR-Code und einen Teilen-Link.
   * Enthält den interaktiven 3D-Viewer mit Animation-Controls, Reset-Funktion und AR-Modus (`WebXR` / `Scene Viewer` / `Quick Look`).

2. **`download.html` (Direct Downloader & Landingpage)**
   * Eine schlanke "Landingpage" für den Empfänger.
   * Triggert beim Aufrufen *sofort* den automatischen Download der Datei im Hintergrund.
   * Bietet einen direkten Button, um das Modell mit einem Klick in AR auf der Viewer-Seite zu öffnen.

---

## Einrichtung & Anpassung

1. Lade beide HTML-Dateien auf deinen Webserver oder GitHub Pages hoch.
2. Öffne die Datei `download.html` und passe in den Scripts (ca. Zeile 57) die URL zu deiner Viewer-Seite an:
   ```javascript
   // WICHTIG: Ersetze dies mit der echten URL deiner Viewer-Seite
   const VIEWER_PAGE_URL = "[https://deine-domain.com/viewer.html](https://deine-domain.com/viewer.html)";
