# 🍺 Trinkspiele

Eine mobile-first Trinkspiele-App als einzelne HTML-Datei – keine Installation, keine Dependencies, läuft direkt im Browser.

**Live:** [netlify.com/drop](https://netlify.com/drop) → Datei raufziehen → fertig.

---

## Spiele

| Spiel | Beschreibung |
|-------|-------------|
| 🎲 **Meyer** | Würfel-Bluff-Spiel. Verdeckt würfeln, Wert ansagen (ehrlich oder Bluff), nächster Spieler glaubt oder zweifelt an. |
| 🥃 **Schocken** | Jeder würfelt 3 Würfel verdeckt, gleichzeitig aufdecken – niedrigstes Ergebnis trinkt. |
| 🎰 **Kniffel Trinkversion** | Yahtzee mit Trinkstrafen: 0 Punkte = 1 Schluck, Kniffel = 5 Schlucke verteilen. |
| ⚡ **Farkle** | Risiko-Würfelspiel: Punkte kassieren oder weiter würfeln. Farkle = alle Punkte weg! |
| 🃏 **Kings / Ring of Fire** | 52-Karten-Deck, jede Karte hat eine feste Regel. 4. König = Kelch leeren. |
| 🖐 **Ich hab noch nie…** | 50+ Aussagen, Finger runter wenn man's getan hat. Wer zuerst alle Finger unten hat, trinkt. |
| 👆 **Most Likely To** | Frage erscheint, alle zeigen auf eine Person – wer am meisten Stimmen hat, trinkt. |
| 🤔 **Would You Rather** | Zwei Optionen, alle stimmen ab – die Minderheit trinkt. |
| 🌀 **Spin the Wheel** | Drehrad mit allen Spielernamen – wen es trifft, trinkt. |
| 💬 **Kategorien** | Kategorie erscheint, 8 Sekunden pro Spieler ein Beispiel nennen – wer stockt, trinkt. |

---

## Features

- **Single File** – alles in einer `trinkspiele.html`, keine Dependencies, kein Build-Step
- **Mobile-first** – optimiert für ~390px, Touch-Targets ≥ 44px
- **Dark Theme** – lila/blau Akzente
- **Animierte Würfel** – CSS Roll-Animation, Halte-Feedback
- **Animiertes Kartenziehen** – CSS 3D Flip
- **Spin-Wheel** – Canvas-basiert mit Physik-Abbremsung
- **Timer-Ring** – SVG Countdown-Ring bei Kategorien
- **Spieler-Setup** – 2–8 Spieler, Namen persistent via localStorage
- **Anleitungen** – Slide-Up Sheet mit detaillierten Regeln für jedes Spiel (ℹ️ Button)
- **Disclaimer** – 18+ Hinweis beim ersten Start (localStorage-Flag)
- **Deutsch** – vollständig deutsche UI

---

## Verwendung

### Lokal
Datei einfach im Browser öffnen:
```
open trinkspiele.html
```

### Handy (gleiches WLAN)
```bash
python3 -m http.server 8080 --directory .
```
Dann auf dem Handy: `http://<mac-ip>:8080/trinkspiele.html`

### Hosting (empfohlen)
Datei auf [netlify.com/drop](https://netlify.com/drop) ziehen → sofortige öffentliche URL.

---

## Spieler verwalten

Unten in der Nav auf **👥 Spieler** tippen → Namen eingeben, hinzufügen oder entfernen. Namen werden automatisch gespeichert.

---

## Disclaimer

> Nur für Personen ab 18 Jahren. Trinkt verantwortungsvoll. Niemals betrunken fahren.
