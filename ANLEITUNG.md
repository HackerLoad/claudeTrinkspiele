<!--
================================================================================
  ANLEITUNG.md – Trinkspiele App
  Vollständige Dokumentation für Nutzer und Entwickler
================================================================================
-->

# Trinkspiele App – ANLEITUNG

---

## 1. Projektübersicht

**Was ist das?**
Eine mobile-first Web-App mit 43 Trink-Spielen für Gruppen. Alles läuft offline im Browser – keine Installation, kein Server, keine externen Abhängigkeiten.

**Technologie-Stack**
- HTML5 / CSS3 / Vanilla JavaScript (ES6+)
- Keine Frameworks, keine Bibliotheken
- LocalStorage für persistente Einstellungen

**Dateistruktur**
```
index.html          ← gesamte App (eine einzige Datei)
```

---

## 2. Installation & Start

### Lokal öffnen
1. `index.html` herunterladen
2. Doppelklick auf die Datei → öffnet im Standard-Browser
3. Fertig – funktioniert offline

### Auf einem Gerät hosten (LAN)
```bash
# Python 3
python3 -m http.server 8080

# Node.js (npx)
npx serve .
```
Dann auf jedem Gerät im WLAN: `http://[deine-IP]:8080`

### Empfohlene Browser
Chrome, Safari, Firefox (aktuell). Optimiert für Smartphone (430px Breite).

---

## 3. Spielerliste einrichten

1. Unten auf **👥 Spieler** tippen
2. Namen der Spieler eingeben (2–8 Spieler)
3. Mit **+ Spieler hinzufügen** weitere Spieler ergänzen
4. Mit **✕** Spieler entfernen
5. **🔞 NSFW-Modus**: Schalter aktivieren für erwachsene Fragen und Inhalte
6. Auf **✓ Fertig** tippen

Die Spielerliste wird automatisch in LocalStorage gespeichert und beim nächsten Öffnen wiederhergestellt.

---

## 4. Navigationsübersicht

### Bottom Navigation
| Icon | Funktion |
|------|----------|
| 🏠 Spiele | Spielübersicht (Startseite) |
| 👥 Spieler | Spielerverwaltung & Einstellungen |

### Kategorie-Tabs (Startseite)
Horizontal scrollbare Tabs filtern die Spielliste:

| Tab | Enthaltene Spiele |
|-----|-------------------|
| Alle | Alle 43 Spiele |
| 🎲 Würfel | Meyer, Schocken, Kniffel, Farkle, 10.000, Pig, Mäxchen, Liar's Dice |
| 🃏 Karten | Kings, Busfahrer, Higher/Lower, Flaschendrehen |
| 🤔 Raten | Ich hab nie, Most Likely, Would You Rather, Wer bin ich?, 2W1L, Promis raten |
| ⚡ Reaktion | Countdown, Heiße Kartoffel, Tap Race, Schnellster Finger |
| 👥 Sozial | Waterfall, Geständnisrunde, Truth Bomb, Hot Takes, Wahr./Pflicht, Story-Kette, Sing/Trink, Wachstumsgebot |
| 🔢 Zahlen | Buzz, Fizz Buzz, Alphabet-Spiel, Kategorien |
| ❓ Quiz | Trink-Quiz, Geografie-Runde |
| 🎨 Kreativ | Zeichnen & Raten, Dare Wheel |
| 🎮 Mini | Memory, Simon Says, Minesweeper, Bierpong, Spin the Wheel |

### ℹ️ Info-Button
Erscheint oben rechts beim Spielen → öffnet Spielanleitung als Bottom Sheet.

---

## 5. Spielanleitungen

### 🎲 WÜRFELSPIELE

#### Meyer
**Ziel:** Würfle höher als der Vorgänger – oder bluff.
**Ablauf:** Verdeckt würfeln → Wert ansagen (ehrlich oder gelogen) → Nächster: Glauben oder Anzweifeln. Angezweifelt + gelogen → Ansager trinkt. Angezweifelt + wahr → Anzweifler trinkt.
**Besonderheit:** Mäxchen (21) = höchster Wert. Kann auch blind (ohne würfeln) weitergegeben werden.
**Touch:** Würfeln-Button → Wert antippen → Handy weitergeben.

#### Schocken
**Ziel:** Nicht das schlechteste Ergebnis haben.
**Ablauf:** Jeder würfelt 3 Würfel verdeckt → gleichzeitig aufdecken → Schlechtestes Ergebnis trinkt.
**Wertung:** Schock-Aus (1-2-3) = schlechtestes. Schock (zwei 1en) = bestes.

#### Kniffel (Trinkversion)
**Ziel:** Wie Yahtzee. Wer am Ende die wenigsten Punkte hat, trinkt.
**Ablauf:** 5 Würfel, 3 Würfe pro Zug. Würfel antippen zum Festhalten. Kategorie wählen.
**Trinkregeln:** 0 Punkte → 1 Schluck. Kniffel → 5 Schlucke verteilen.

#### Farkle
**Ziel:** Punkte sammeln. Letzter mit den wenigsten trinkt.
**Ablauf:** 6 Würfel würfeln → Punkte-Würfel festhalten → kassieren oder weiter riskieren. Kein Punkte-Würfel = Farkle (alle Rundenpunkte weg). Mind. 300 Punkte zum Kassieren.

#### 10.000
**Ziel:** Als erster 10.000 Punkte. Wer am Ende am wenigsten hat, trinkt.
**Ablauf:** Wie Farkle aber: mind. 1000 zum Öffnen. Straight (1-6) = 2000 Punkte. 3 Paare = 1500.

#### Pig
**Ziel:** Erste zu 100 Punkte. Letzter trinkt.
**Ablauf:** 1 Würfel. Würfeln und Punkte sammeln oder banken. Eine 1 = Runden-Topf verloren.

#### Mäxchen
**Ziel:** Wie Meyer, vereinfacht (kein blind Weitergeben).
**Trinkregel:** Gelogen und erwischt = 2 Schlucke. Mäxchen wahrheitsgemäß = alle anderen trinken.

#### Liar's Dice
**Ziel:** Biete auf die Gesamtzahl einer Augenzahl aller Spieler – oder bluff.
**Ablauf:** Jeder würfelt 5 Würfel verdeckt → Biete reihum ("Mind. X Würfel zeigen Zahl Y") → Gebot muss höher → "Lüge!" rufen → aufdecken.
**Trinkregel:** Gebot stimmte → Rufer trinkt. Gebot falsch → Bieter trinkt.

---

### 🃏 KARTENSPIELE

#### Kings / Ring of Fire
**Ablauf:** Reihum Karte ziehen. Jede Karte hat eine Regel (Ass = Wasserfall, König = König-Kelch, etc.).
**Besonderheit:** Wer den 4. König zieht, muss den Kelch leeren!

#### Busfahrer
**Ablauf:** 4 Fragen über die nächste Karte beantworten: (1) Rot/Schwarz? (2) Höher/Tiefer? (3) Innen/Außen? (4) Welche Farbe?
**Trinkregel:** Jede falsche Antwort = 1 Schluck. Alle 4 richtig = 2 Schlucke verteilen!

#### Higher or Lower
**Ablauf:** Karte aufgedeckt → Höher oder Tiefer für die nächste Karte tippen.
**Trinkregel:** Falsch = so viele Schlucke wie der aktuelle Streak.

#### Flaschendrehen (digital)
**Ablauf:** Rad drehen → Pflicht-Karte erscheint → ausführen oder trinken.

---

### 🤔 RATESPIELE

#### Ich hab noch nie…
**Ablauf:** Aussage erscheint ("Ich hab noch nie…"). Alle die es getan haben, senken einen Finger (−-Taste).
**Trinkregel:** Wer alle 5 Finger unten hat, trinkt!

#### Most Likely To
**Ablauf:** Frage erscheint ("Am ehesten…"). Alle tippen auf eine Person.
**Trinkregel:** Meistgenannte Person trinkt so viele Schlucke wie Stimmen auf sie.

#### Would You Rather
**Ablauf:** Zwei Optionen. Jeder wählt A oder B. Die Minderheit trinkt.

#### Wer bin ich?
**Ablauf:** Jeder bekommt heimlich einen Promi zugewiesen. Stelle Ja/Nein-Fragen. 10 Fragen pro Runde.
**Trinkregel:** Nicht erraten = trinken. Erraten = Drinks verteilen.

#### 2 Wahrheiten, 1 Lüge
**Ablauf:** Spieler gibt 3 Aussagen ein (2 wahr, 1 gelogen). Alle stimmen ab welche die Lüge ist.
**Trinkregel:** Falsch geraten = trinken. Alle falsch = Spieler verteilt 2 Schlucke.

#### Promis raten
**Ablauf:** Hinweise über einen Promi erscheinen Schritt für Schritt. Wer ihn zuerst erkennt, verteilt Schlucke.
**Trinkregel:** Niemand weiß es = alle trinken.

---

### ⚡ REAKTIONSSPIELE

#### Countdown
**Ablauf:** Versteckter Timer (5–15 Sek.) startet. Wenn Signal erscheint: so schnell wie möglich tippen. Jeder Spieler wird einzeln getestet.
**Trinkregel:** Langsamste Reaktionszeit trinkt.

#### Heiße Kartoffel
**Ablauf:** Timer startet (5–20 Sek. zufällig). Handy weitergeben. Wer es hält wenn der Timer endet, trinkt!

#### Tap Race
**Ablauf:** Jeder Spieler tippt 5 Sekunden so oft wie möglich auf den Bildschirm (sequentiell).
**Trinkregel:** Wenigste Taps = trinken.

#### Schnellster Finger
**Ablauf:** 3 Reaktions-Tests pro Spieler. Wenn "JETZT!" erscheint: sofort tippen.
**Trinkregel:** Langsamste Durchschnittszeit = trinken.

---

### 👥 SOZIALE SPIELE

#### Waterfall
**Ablauf:** Alle trinken gleichzeitig. Spieler 1 hört auf wann er will. Jeder folgende darf erst aufhören wenn der Vorgänger aufgehört hat.

#### Geständnisrunde
**Ablauf:** Jeder gibt anonym ein Geständnis ein. Alle raten von wem es stammt.
**Trinkregel:** Falsch geraten = trinken.

#### Truth Bomb
**Ablauf:** Fragen über die Gruppe erscheinen ("Wer würde…?"). Alle stimmen ab.
**Trinkregel:** Meistgenannte Person trinkt.

#### Hot Takes
**Ablauf:** Provokante Aussagen. Zustimmen oder Ablehnen.
**Trinkregel:** Minderheit trinkt. Gleichstand = alle kommen davon.

#### Wahrheit oder Pflicht
**Ablauf:** Spieler wählt Wahrheit oder Pflicht. Prompt erscheint. 1× überspringen erlaubt.
**Trinkregel:** Verweigern = doppelt trinken. 50+ Wahrheiten und 50+ Pflichten eingebaut.

#### Story-Kette
**Ablauf:** Story-Starter erscheint. Jeder fügt einen Satz hinzu (Texteingabe).
**Trinkregel:** Kein Satz oder Logik gebrochen = trinken.

#### Sing oder Trink
**Ablauf:** Gesangsaufgabe erscheint. Mind. 5 Sek. singen. Gruppe entscheidet.
**Trinkregel:** Nicht bestanden = trinken.

#### Wachstumsgebot
**Ablauf:** Spieler 1 nennt eine Aktion. Spieler 2 wiederholt alles und fügt eine hinzu. Usw.
**Trinkregel:** Aktion vergessen = trinken. Kette wird angezeigt – aber aus dem Gedächtnis aufsagen!

---

### 🔢 ZAHLENSPIELE

#### Buzz
**Ablauf:** Reihum von 1 zählen. Vielfache von 7 und Zahlen mit 7 = "BUZZ!".
**Buzz-Zahlen:** 7, 14, 17, 21, 27, 28, 35, 42, 47, 49, 56, 63, 67, 70–79, 84, ...
**Trinkregel:** Falsch = trinken + Neustart bei 1.

#### Fizz Buzz
**Regeln:** 3 = Fizz · 5 = Buzz · 15 = FizzBuzz · sonst Zahl.
**Trinkregel:** Falsch = trinken + Neustart.

#### Alphabet-Spiel
**Ablauf:** Kategorie + Buchstabe erscheinen. Reihum Wörter nennen die mit dem Buchstaben beginnen. 8 Sekunden pro Spieler.
**Trinkregel:** Zeit abgelaufen oder Wiederholung = trinken.

#### Kategorien
**Ablauf:** Kategorie erscheint. 8 Sekunden pro Spieler ein Beispiel nennen.
**Trinkregel:** Zeit abgelaufen = trinken.

---

### ❓ QUIZ & WISSEN

#### Trink-Quiz
**Ablauf:** Multiple-Choice-Fragen (4 Optionen). Spieler tippen nacheinander. 100+ Fragen in 4 Kategorien.
**Trinkregel:** Falsch = trinken. Richtig = 1 Schluck verteilen.
**Kategorien:** Allgemeinwissen, Popkultur, Sport, Geschichte.

#### Geografie-Runde
**Ablauf:** Wie Trink-Quiz, fokussiert auf Geografie und Hauptstädte.

---

### 🎨 KREATIVSPIELE

#### Zeichnen & Raten
**Ablauf:** Aktueller Spieler bekommt ein Wort (nur für ihn). Zeichnet auf dem Canvas. Andere raten.
**Touch:** Finger auf Canvas → malen. Löschen-Button zum Zurücksetzen.
**Trinkregel:** Letzter der rät (oder niemand rät) = trinken.
**Einschränkung:** Nur lokal auf einem Gerät nutzbar – kein Netzwerk-Multiplayer.

#### Dare Wheel
**Ablauf:** Rad drehen → zufällige Pflicht erscheint. Ausführen oder doppelt trinken.

---

### 🎮 MINIGAMES

#### Memory (Trinkversion)
**Ablauf:** 16 verdeckte Karten (8 Emoji-Paare). Zwei aufdecken pro Zug. Treffer = Paar gewonnen.
**Trinkregel:** Kein Treffer = trinken + Karten zurückdrehen. Wenigste Paare am Ende = extra trinken.

#### Simon Says (Trinkversion)
**Ablauf:** 4 farbige Felder leuchten in Reihenfolge auf → wiederholen. Jede Runde ein Schritt mehr.
**Trinkregel:** Falsche Reihenfolge = trinken + Neustart bei Runde 1.

#### Minesweeper (Trinkversion)
**Ablauf:** 5×5 Gitter, 6 versteckte Minen. Reihum eine Kachel aufdecken.
**Trinkregel:** Mine getroffen = trinken. Alle anderen Kacheln aufdecken = Drinks verteilen!

#### Bierpong Scoreboard
**Ablauf:** Digitales Scoreboard für physisches Bierpong. 2 Teams, je 10 Becher. Getroffene Becher antippen.
**Hinweis:** Reines Scoreboard – der Ball bleibt physisch!

#### Spin the Wheel
**Ablauf:** Rad dreht sich und zeigt zufällig auf einen Spieler.
**Trinkregel:** Gezeigter Spieler trinkt.

---

## 6. Technische Dokumentation

### Architektur-Übersicht

```
index.html
├── <style>          CSS-Variablen, alle Komponenten-Styles
├── <body>           HTML-Screens (eine div pro Spiel)
└── <script>
    ├── Utilities    roll(), shuffle(), toast(), dieSvg()...
    ├── App          globaler State { players, current, nsfw, catFilter }
    ├── GAME_META    Array aller Spiele mit ID, Icon, Name, Kategorie
    ├── CATS_DEF     Kategorie-Definitionen für die Tabs
    ├── NAV_ITEMS    Bottom-Navigation
    ├── RULES_DATA   Anleitungen (HTML-Strings) pro Spiel
    ├── GAMES        Objekt – jedes Spiel als IIFE
    └── boot()       Initialisierung
```

### State Management

Jedes Spiel nutzt ein lokales `let S = {}` (IIFE-Scope). Das Muster:

```javascript
GAMES.meinspiel = (function(){
  let S = {};                    // lokaler State

  function render(){             // vollständiges Re-render
    const sc = $('screen-meinspiel');
    sc.innerHTML = `...`;
  }

  return {
    init(){ S = { phase:'intro', ... }; render(); },
    // weitere Methoden
  };
})();
```

### Routing

```javascript
function go(id){
  // alle Screens verstecken
  // screen-{id} aktivieren
  // App.current = id
  // buildNav() aktualisiert Bottom-Nav-Highlighting
  // GAMES[id]?.init() startet das Spiel
}
```

### LocalStorage-Schlüssel

| Schlüssel | Inhalt |
|-----------|--------|
| `ts_players` | JSON-Array der Spielernamen |
| `ts_nsfw` | `"1"` oder `"0"` |
| `ts_ok` | `"1"` wenn Disclaimer akzeptiert |

### Neues Spiel hinzufügen – Schritt für Schritt

**1. Screen-Div hinzufügen** (nach den bestehenden Screens):
```html
<div id="screen-meinspiel" class="screen"></div>
```

**2. GAME_META-Eintrag** (im `GAME_META`-Array):
```javascript
{id:'meinspiel', ic:'🎮', n:'Mein Spiel', d:'Kurzbeschreibung', cat:'minigames'},
```

**3. RULES_DATA-Eintrag** (im `RULES_DATA`-Objekt):
```javascript
meinspiel: {
  title: '🎮 Mein Spiel – Anleitung',
  html: `<h3>Ziel</h3><p>...</p>`
},
```

**4. Spiel-Implementierung** (vor `boot()`):
```javascript
GAMES.meinspiel = (function(){
  let S = {};
  function render(){
    $('screen-meinspiel').innerHTML = `
      <div class="hdr">
        <button class="back-btn" onclick="go('home')">←</button>
        <span class="hdr-emoji">🎮</span>
        <span class="hdr-title">Mein Spiel</span>
      </div>
      <div class="cnt">...</div>
    `;
  }
  return {
    init(){ S = {}; render(); }
  };
})();
```

### CSS-Design-Variablen

```css
--bg:        #0d0d1a  /* Hintergrund */
--surface:   #1a1a2e  /* Karten/Panels */
--surface2:  #252542  /* Inputs/Buttons */
--accent:    #6C63FF  /* Primärfarbe (Lila) */
--accent2:   #FF6584  /* Sekundärfarbe (Pink) */
--text:      #e8e8f0  /* Haupttext */
--muted:     #8888aa  /* Gedämpfter Text */
--border:    #2e2e52  /* Rahmen */
--danger:    #FF4444  /* Rot/Fehler */
--success:   #00C896  /* Grün/Erfolg */
--gold:      #FFD700  /* Gold */
```

### Nützliche Utility-Funktionen

```javascript
$(id)           // document.getElementById(id)
roll(n=6)       // Zufallszahl 1..n
rollN(count)    // Array von count Würfelwürfen
rnd(array)      // zufälliges Element aus Array
shuffle(array)  // Fisher-Yates Shuffle, gibt neues Array zurück
toast(msg, dur) // Toast-Nachricht (Standard: 3,2 Sek.)
dieSvg(val, held, small)  // Würfel-HTML generieren
animDice(selector)        // Würfel-Animation anstoßen
```

---

## 7. Bekannte Einschränkungen

| Einschränkung | Details |
|---------------|---------|
| **Ein Gerät** | Alle Spiele sind für ein geteiltes Gerät konzipiert. Kein Netzwerk-Multiplayer. |
| **Zeichnen & Raten** | Canvas-Zeichnung nur lokal. Alle Spieler müssen zum Raten am selben Gerät sein. |
| **Reaktionsspiele** | Countdown, Schnellster Finger und Tap Race testen Spieler sequentiell (nicht gleichzeitig). |
| **Heiße Kartoffel** | Gerät muss sichtbar sein damit alle den Timer beobachten können. Kein Vibrations-Feedback. |
| **Kein Netzwerk** | Keine Online-Highscores, kein Sync zwischen Geräten. |
| **Kein Audio** | Kein Sound/Musik (Browser-Autoplay-Beschränkungen). |
| **Kein Zurück im Browser** | Browser-Back-Button navigiert raus aus der App. Den ← Button in der App nutzen. |
| **LocalStorage** | Spielernamen und Einstellungen bleiben nur auf demselben Browser/Gerät gespeichert. |
| **Liar's Dice** | Vertrauensbasiert – jeder Spieler sieht seine Würfel kurz, bevor er das Handy weitergibt. |

---

## 8. Erweiterungshinweise

### Eigene Quiz-Fragen hinzufügen
Im `QUIZ_DB`-Array (vor `GAMES.trinkquiz`):
```javascript
{
  q: 'Frage?',
  o: ['Option A', 'Option B', 'Option C', 'Option D'],
  a: 2,           // Index der richtigen Antwort (0-basiert)
  cat: 'Allgemeinwissen'  // oder Popkultur / Sport / Geschichte
}
```

### Eigene Wahrheit/Pflicht-Prompts
Im `TRUTHS`- bzw. `DARES`-Array in `GAMES.wahrheitpflicht`:
```javascript
const TRUTHS = [ 'Neue Wahrheit?', ... ];
const DARES  = [ 'Neue Pflicht!', ... ];
```

### Eigene "Ich hab noch nie"-Aussagen
Im `SAFE`- oder `NSFW`-Array in `GAMES.nochnie`:
```javascript
const SAFE = [ 'neue Aussage', ... ];
const NSFW = [ 'erwachsene Aussage', ... ]; // nur bei NSFW-Modus aktiv
```

### Eigene Promis für "Wer bin ich?"
Im `CELEBS`-Array in `GAMES.werbinici`:
```javascript
const CELEBS = shuffle(['Neuer Promi', 'Bekannte Figur', ...]);
```

### Neues Rad-Segment für Dare Wheel
Im `DARES_W`-Array in `GAMES.darewheel`:
```javascript
const DARES_W = ['Neue Pflicht', ...];
```

### Neue Spielkategorie
Im `CATS_DEF`-Array:
```javascript
const CATS_DEF = [
  ...
  {id:'neuekat', label:'🆕 Neue Kategorie'},
];
```
Dann Spiele mit `cat:'neuekat'` im `GAME_META` registrieren.

### Design anpassen
CSS-Variablen in `:root {}` am Anfang der `<style>`-Sektion ändern. Alle Farben, Abstände und Radien sind dort zentralisiert.

---

*Trinkspiele App – Vanilla JS, Single File, No Dependencies*
*© Maxim Andris*