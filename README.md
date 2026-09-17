# B1 Deutsch Trainer – PWA mit Content-Update-System

Die App muss nach der ersten Installation nicht neu installiert werden. Lerninhalte werden getrennt vom App-Code verwaltet.

## Relevante Dateien

- `content/b1-content.json` – alle Lerninhalte
- `content/version.json` – Versionsmeldung und Release Notes
- `index.html` – App und Update-Logik
- `service-worker.js` – Offline-PWA

## Neue Inhalte veröffentlichen

1. `content/b1-content.json` erweitern oder austauschen.
2. In `content/version.json` unbedingt `contentVersion` erhöhen.
3. Optional Titel, Nachricht, Release Notes und Zähler anpassen.
4. Commit + Push auf GitHub.
5. GitHub Pages veröffentlicht das Update.
6. Die installierte App prüft beim Start und später regelmäßig `version.json` ohne Cache.
7. Der Nutzer sieht **NEUE INHALTE** und kann **Jetzt aktualisieren** oder **Später** wählen.
8. Beim Update bleiben Lernfortschritt und Fehlerbuch erhalten.

## Beispiel version.json

```json
{
  "contentVersion": "2026.09.18.1",
  "publishedAt": "2026-09-18T10:00:00+02:00",
  "title": "Update: Arbeit & Behörden",
  "message": "35 neue Übungen sind verfügbar.",
  "releaseNotes": [
    "20 neue Aufgaben zu Arbeit und Beruf",
    "10 neue Behörden-Dialoge",
    "5 neue Schreibaufgaben"
  ],
  "counts": {
    "Grammatik": 50,
    "Wortschatz": 60,
    "Lesen": 40,
    "Hören": 20,
    "Schreiben": 20,
    "Sprechen": 20
  },
  "contentUrl": "./content/b1-content.json",
  "minAppVersion": "3.0.0",
  "force": false
}
```

## Offline

Die zuletzt erfolgreich installierte Inhaltsversion bleibt offline nutzbar. Falls ein Update fehlschlägt, bleibt die bisherige Version aktiv.

## Versionsschema

- App-Code: z. B. `3.0.0`
- Inhalte: Datum + laufende Nummer, z. B. `2026.09.18.1`

GitHub Pages: `https://empishaj.github.io/b1-app/`
