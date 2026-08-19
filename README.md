# Kroatisch Tutor

Private, local-first Kroatisch-Vokabel-PWA für deutsche Muttersprachler.

## Was neu ist (v3)
- **40 Lektionen / 398 Wörter** (Grüßen, Zahlen, Café, Farben, Familie, Wochentage, Monate, Zeit, Wetter, Körper, Kleidung, Zuhause, Essen, Obst & Gemüse, Getränke, Verben, Adjektive, Fragewörter, größere Zahlen, Richtungen, Verkehr, Reisen & Hotel, Gesundheit, Stadt, Einkaufen, Berufe, Tiere, Natur, Gefühle, Small Talk, Wegbeschreibung, Zeitausdrücke, Haushalt, Arbeit & Schule, Technologie, Sport & Hobbys, Feste & Jahreszeiten)
- Bei **10 neuen Wörtern pro Tag** reicht das für ca. **1,5 Monate** Kerninhalt – plus die Wiederholungen, die durch das Spaced-Repetition-System täglich dazukommen. Für den vollen 6-Monats-Umfang (~1800 Wörter) lässt sich die App in weiteren Runden genau so aufstocken, ohne den Code zu ändern (siehe unten).
- **Quiz wird jetzt automatisch generiert** statt von Hand für jede Lektion geschrieben – zieht zufällig 6 Wörter der Lektion, fragt zufällig in beide Richtungen (DE→HR / HR→DE) ab und mischt die Antwortoptionen. Dadurch skaliert die App beliebig ohne Mehraufwand pro Lektion.
- **Echtes Spaced Repetition** (Leitner-System): Wörter kommen je nach Erfolg nach 1/2/4/8/16 Tagen zur Wiederholung zurück
- **Wiederholungs-Modus**: fällige Wörter werden zufällig in beide Richtungen abgefragt
- **Echte App-Icons** (192/512/Apple-Touch-Icon) für ein sauberes Home-Bildschirm-Symbol
- **Fehlertoleranter Storage**: funktioniert auch, wenn `localStorage` blockiert ist (z. B. privates Surfen)
- **Dark Mode** folgt automatisch den System-Einstellungen
- Service Worker-Cache auf v3 angehoben, damit bereits installierte Apps das Update laden

## Sicherheit/Privatsphäre (unverändert)
- kein Konto
- keine Analyse/Werbung
- keine Skripte von Dritten
- keine Geräte-Berechtigungen
- Lernstand nur lokal gespeichert
- manueller JSON-Export/Löschen
- Offline-Cache für die Kern-App

Die App selbst sendet keine Lerndaten an einen Server. Normales Website-Hosting kann trotzdem technisch notwendige Netzwerk-Metadaten (IP, Zeitstempel) beim Hoster sichtbar machen.

## Per GitHub Pages veröffentlichen

1. Neues GitHub-Repository anlegen (z. B. `kroatisch-tutor`).
2. Diese Dateien in den Repo-Root legen:
   ```
   index.html
   manifest.json
   sw.js
   icons/icon-192.png
   icons/icon-512.png
   icons/apple-touch-icon.png
   README.md
   ```
3. Committen und pushen (`git add . && git commit -m "Kroatisch Tutor v2" && git push`).
4. Im Repo: **Settings → Pages → Source: Deploy from a branch**, Branch `main`, Ordner `/root` auswählen, speichern.
5. Nach ein bis zwei Minuten ist die App unter `https://DEIN-USERNAME.github.io/kroatisch-tutor/` erreichbar.

## Auf dem iPhone installieren
Seite in Safari öffnen → Teilen-Symbol → **Zum Home-Bildschirm** → **Hinzufügen**. Danach läuft sie als eigenständige App mit eigenem Icon, ohne Safari-Leiste.

## Lektionen erweitern
Neue Lektion = neuer Eintrag im `LESSONS`-Array in `index.html`. Format pro Wort:
`[kroatisch, deutsch, aussprache, beispiel_hr, beispiel_de, merktipp]`. Die App skaliert automatisch mit beliebig vielen Wörtern pro Lektion.
