# MapQuizzzes (MapQuizzzes-de)

**MapQuizzzes** ist ein flexibles, webbasiertes Framework zur Erstellung von interaktiven, GPS-gestützten Outdoor-Rätseltouren für das Smartphone. Es läuft vollständig im Browser des Nutzers, ist als Progressive Web App (PWA) installierbar und erfordert keine Anmeldung für den Benutzer.


**English version:** **[https://github.com/ahrenstk/MapQuizzzes](https://github.com/ahrenstk/MapQuizzzes)**

**Dutch version:** **[https://github.com/ahrenstk/MapQuizzzes-nl](https://github.com/ahrenstk/MapQuizzzes-nl)**



---

## 🚀 Live-Demo

Du kannst dir das Live-Demo **[Bourtange-Quiz](https://ahrens.tk/MapQuizzzes)** anschauen. Stell dir vor du würdest die **[Festung Bourtange](https://www.bourtange.de)** besuchen und es dort vor Ort spielen. Auch kannst du dir das **[Münster-Quiz](https://ahrens.tk/muensterquiz)** anschauen und falls du mal im schönen Münster bist vor Ort die Quiz-Fragen beantworten.

---

## 🛠️ Für wen ist MapQuizzzes die perfekte Lösung?

**MapQuizzzes** schlägt die Brücke zwischen Entdeckergeist und digitaler Interaktion. Es ist das ideale Werkzeug für alle, die Menschen spielerisch bewegen, begeistern und Wissen direkt vor Ort erlebbar machen wollen. 

### 🌟 Perfekt geeignet für:
* **Tourismus- & Stadtmarketing-Experten:** Verwandle klassische Stadtführungen in packende, interaktive Entdeckertouren und ziehe Besucher spielerisch in den Bann deiner Region.
* **Erlebnispädagogen & Schulen:** Gestalte moderne, GPS-gestützte Schnitzeljagden und interaktive Lernpfade an der frischen Luft.
* **Event-Agenturen & Teambuilding-Anbieter:** Kreiere maßgeschneiderte Outdoor-Rallyes für Firmen-Events, Vereinsausflüge oder private Feiern.
* **Kreative Köpfe & Abenteurer:** Erstelle ganz einfach deine eigene, persönliche Rätseltour für Freunde und Familie.

---

### 💡 Dein Weg zum eigenen Outdoor-Quiz

Das Beste vorweg: **MapQuizzzes ist komplett kostenlos!** Dein Weg zum eigenen MapQuizzz ist denkbar einfach:

1. **Blitzschnelles Setup:** Entpacke die Software einfach in ein Verzeichnis auf deinem Webserver – und die technische Basis steht bereits.
2. **Kreative Gestaltung:** Der spannendste Teil liegt bei dir – das Erwecken deiner Tour zum Leben! Du bestimmst die Orte, die Rätselfragen und die Belohnungen. 
3. **Direkter Start:** Damit du sofort siehst, was möglich ist, wird MapQuizzzes mit einer **vollwertigen Demo-Tour** ausgeliefert. Diese zeigt dir direkt alle vier flexiblen Tour-Modi in Aktion und dient dir als perfekte, leicht verständliche Vorlage für dein eigenes Meisterwerk.


---

## ✨ Features

- **Reine Browser-Anwendung:** Die gesamte Logik läuft im Browser. Es findet keine serverseitige Datenspeicherung statt. Auch im Browser werden keine Daten wie Cookies oder IndexedDB gespeichert.
- **PWA-Ready:** Kann wie eine native App zum Startbildschirm von Android- und iOS-Geräten hinzugefügt werden.
- **Keine Anmeldung:** Nutzer können sofort und ohne Konto loslegen.
- **Interaktive Karten:** MapQuizzzes nutzt mit Leaflet das Kartenmaterial von OpenStreetMap und Esri.
- **GPS-Navigation:** Zeigt den eigenen Standort an und bietet eine Navigationsfunktion zu den Rätselorten per Google Maps
- **Flexible Tour-Modi:**
    - **Schritt für Schritt:** Schaltet das nächste Rätsel erst nach dem Lösen des vorherigen frei.
    - **Ganze Karte:** Alle Rätsel sind von Anfang an sichtbar inkl. GPX-Track
    - **Luftlinie:** "Ähnlich Schritt für Schritt" jedoch mit Luflinie ohne GPX-Track
    - **Freestyle:** Ähnlich "Ganze Karte" aber ohne GPX-Track
- **Vielseitige Rätsel:**
    - Multiple-Choice-Fragen oder offene Fragen (jeweils 3 Sekunden Antwortzeit)
    - Tipps aber auch Fragen können optional verwendet werden
    - für jeden Ort wird ein Bild verwendet
    - optional können zu jedem Ort weitere Modals geöffnet und auch Links zu externen Webseiten verwendet werden
- **Anpassbar & Erweiterbar:** Alle Touren, Rätsel und Texte werden über einfache `JSON`-Dateien konfiguriert.
- **Mehrsprachigkeit:** Das Design ist von Grund auf mehrsprachig und kann leicht um weitere Sprachen erweitert werden
- **Open Source:** Veröffentlicht unter der MIT-Lizenz

---

## 🛠️ Technische Struktur

1. `/index.php`: Hauptprogramm, welches unter anderem die Hauptkonfiguration (`MapQuizzzes.json`) lädt
2. `/MapQuizzzes.json`: Hauptkonfiguration für Sprache, Startseite sowie Tourenauswahl (Unterverzeichnisse jeweils inkl. `quizdata.json`)
3. `/Tourname/quizdata.json`: Konfigurationsdatei für eine Einzeltour mit JSON-Objekte für jede Ort mit Bildname, Koordinaten, Fragen, Tipps, Antworten, ..)
4. `js/MapQuizzzes.js` und `css/MapQuizzzes.css`: JavaScript und CSS von MapQuizzzes

---

## 🚀 Eigene Quiz-Tour erstellen

MapQuizzzes ist **kein** Baukasten-System zur Erstellung von interaktiven Quizzzes. Aber mit ein wenig Übung ist es nicht schwierig eigene Rätseltouren zu erstellen:

1. **Unterordner löschen oder umbenennen:**
   -   im Demo Festung (Schritt für Schritt), Festung (Ganze Karte), Festung (Luftlinie), Festung (Freestyle)

2. **Neue Unterordner für jede Tour anlegen oder umbennnen**
   - z. B. `Meine erste Tour`, `Meine zweite Tour` 

3. **MapQuizzzes.json anpassen:**
    - eigener Quiz-Name, Infos für Starseite, Eintragen der Touren z. B. `Meine erste Tour`, `Meine zweite Tour` 

4. **Notwendige Dateien in den Tour-Ordner kopieren:**
   - Bilder in zwei Auflösungen, verwende gerne `upload.php` aus den Demo-Tourordnern zur automatischen Erstellung der korrekten Bildgrößen
   - optional weitere Zusatzinfos zusammenstellen (modalheader, modalfooter, modalextra)

4. **`quizdata.json` je Tour anpassen:**
    - `quizdata.json`-Datei vom Demo kopieren und für die eigene Tour anpassen
    - jedes JSON-Objekt enthält die für jeden einzelnen Ort benötigten Daten

5. **Anleitung, Impressum, Datenschutz anpassen:**
   - Passe die Dateien an oder erstelle sie für deine Zwecke neu. Impressum und Datenschutz kannst du auch extern verlinken.

Fertig! Deine MapQuizzzes-Instanz mit deinen Touren ist fertig und einsatzbereit. 

---

## 📄 Lizenz

Dieses Projekt steht unter der **MIT-Lizenz**. Die Lizenzdetails findest du in der `LICENSE`-Datei.
