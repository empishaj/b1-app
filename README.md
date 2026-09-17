# B1 Deutsch Trainer 3.1.0 – Lernpaket 2

## Neue Version
- App-Version: `3.1.0`
- Content-Version: `2026.09.17.2`
- Neue Übungen: `108`
- Gesamtbestand: `269` Trainingseinheiten

## Update-Verhalten für bereits installierte PWAs
Beim nächsten Start mit Internetverbindung lädt die PWA die aktuelle `index.html` und prüft `content/version.json` mit `cache: no-store`.

Da `force: true` gesetzt ist, erscheint ein bildschirmfüllender Hinweis **„Erforderliches Lernpaket“**. Die App muss nicht neu installiert werden. Der Benutzer tippt nur auf **„Jetzt Lernpaket aktualisieren“**. Danach wird `content/b1-content.json` geladen und lokal gespeichert.

Lernfortschritt, Statistik und Fehlerbuch bleiben im `localStorage` erhalten.

## Was wurde ergänzt?
- +30 Grammatik
- +40 Wortschatz
- +14 Lesen
- +8 Hören
- +8 Schreiben
- +8 Sprechen

## Deployment
Diese Dateien im Repository ersetzen/ergänzen und anschließend auf den GitHub-Pages-Branch pushen:

- `index.html`
- `service-worker.js`
- `content/b1-content.json`
- `content/version.json`

Die Icons und `manifest.webmanifest` können unverändert bleiben.

## Künftige reine Inhaltsupdates
Wenn die Update-Logik 3.1.0 einmal verteilt ist, reichen für normale Inhaltsupdates in der Regel nur noch:

1. `content/b1-content.json` ändern
2. `content/version.json` auf eine neue `contentVersion` setzen
3. `newItems`, `delta`, `releaseNotes` und `counts` aktualisieren
4. `force` je nach gewünschtem Verhalten auf `true` oder `false` setzen
5. Commit + Push

Die installierte App erkennt das Update beim nächsten Online-Start automatisch.
