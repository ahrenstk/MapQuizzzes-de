# MapQuizzzes

**MapQuizzzes** ist ein flexibles, webbasiertes Framework zur Erstellung von interaktiven, GPS-gestützten Outdoor-Rätseltouren für das Smartphone. Es läuft vollständig im Browser des Nutzers, ist als Progressive Web App (PWA) installierbar und erfordert keine Anmeldung oder Datenspeicherung auf einem Server.


---

## 🚀 Live-Demo

Du kannst dir das Live-Demo **[Bourtange-Quiz](https://ahrens.tk/MapQuizzzes)** anschauen. Stell dir vor du würdest die **[Festung Bourtange](https://www.bourtange.de)** vor Ort besuchen und es dort vor Ort spielen. Auch kannst du dir das **[Münster-Quiz](https://ahrens.tk/muensterquiz)** anschauen und in Münster vor Ort die Quiz-Fragen beantworten.

---

## ✨ Features

- **Reine Browser-Anwendung:** Die gesamte Logik läuft im Browser. Es ist keine serverseitige Datenspeicherung statt
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
- **Open Source:** Veröffentlicht unter der MIT-Lizenz.

---

## 🛠️ Technische Struktur

1. **`index.php`**: Lädt die Hauptkonfiguration (`MapQuizzzes.json`), erkennt die Sprache und stellt die HTML-Grundstruktur sowie die Konfigurationsdaten für die JavaScript-App bereit. Dient auch als API-Endpunkt, um die Daten einer ausgewählten Tour (`quizdata.json`) zu laden.
2. **`MapQuizzzes.js`**: Das Herzstück der Anwendung
3. **Konfigurationsdateien (`.json`)**:
    - **`MapQuizzzes.json`**: Globale Konfiguration (Name, verfügbare Touren, UI-Übersetzungen).
    - **`quizdata.json`**: Enthält alle Rätselpunkte für eine bestimmte Tour (Koordinaten, Fragen, Antworten, Bilder).

---

## 🚀 Eigene Quiz-Tour erstellen

Um eine eigene Rätseltour zu erstellen, sind nur wenige Schritte nötig:

1. **Unterordner löschen oder umbenennen:**
   -   Festung (Schritt für Schritt), Festung (Ganze Karte), Festung (Luftlinie), Festung (Freestyle)

2. **Neue Unterordner für jede Tour anlegen oder umbennnen**
   - z. B. `Meine Tour`

3. **MapQuizzzes.json anpassen:**
    - eigener Quiz-Name, Infos für Starseite, Eintragen der Touren z. B. "Meine Tour"

4. **Notwendige Dateien in den Tour-Ordner kopieren:**
   - Bilder in zwei Auflösungen, verwende gerne `upload.php` aus den Demo-Tourordnern
   - optional Zusatzinfos zusammenstellen (modalheader, modalfooter, modalextra)

4. **`quizdata.json` je Tour anpassen:**
    - Erstellen oder Kopien `quizdata.json`-Datei
    - jedes JSON-Objekt enthält die für jeden einzelnen Ort benötigten Daten


Fertig! Deine MapQuizzzes-Instanz mit deiner Tour "Meine Tour" ist fertig und einsatzbereit. 

---

## 📄 Lizenz

Dieses Projekt steht unter der **MIT-Lizenz**. Die Lizenzdetails finden Sie in der `LICENSE.txt`-Datei.
