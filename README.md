# MapQuizzzes

**MapQuizzzes** ist ein flexibles, webbasiertes Framework zur Erstellung von interaktiven, GPS-gestützten Outdoor-Rätseltouren. Es läuft vollständig im Browser des Nutzers, ist als Progressive Web App (PWA) installierbar und erfordert keine Anmeldung oder Datenspeicherung auf einem Server.

Ein privates Projekt von Heinz Ahrens.

---

## 🚀 Live-Demo

Entdecken Sie das **[Bourtange-Quiz](https://ahrens.tk/MapQuizzzes-de)**, um das Framework in Aktion zu sehen.

- **Andere Sprachen:** [English](https://ahrens.tk/MapQuizzzes-en) | [Nederlands](https://ahrens.tk/MapQuizzzes-nl)
- **Download:** Das gesamte Projekt kann als ZIP-Archiv heruntergeladen werden: [EN](https://ahrens.tk/MapQuizzzes-en.zip), [DE](https://ahrens.tk/MapQuizzzes-de.zip), [NL](https://ahrens.tk/MapQuizzzes-nl.zip)

---

## ✨ Features

- **Komplett im Browser:** Die gesamte Logik läuft clientseitig. Es ist keine serverseitige Datenbank oder Anwendungslogik erforderlich.
- **PWA-Ready:** Kann wie eine native App zum Startbildschirm von Android- und iOS-Geräten hinzugefügt werden.
- **Keine Anmeldung:** Nutzer können sofort und ohne Konto loslegen.
- **Interaktive Karten:** Basiert auf Leaflet.js mit Kartenmaterial von OpenStreetMap und Esri.
- **GPS-Navigation:** Zeigt den eigenen Standort an und bietet eine Navigationsfunktion zu den Rätselorten.
- **Flexible Tour-Modi:**
    - **Schritt für Schritt:** Schaltet das nächste Rätsel erst nach dem Lösen des vorherigen frei.
    - **Ganze Karte:** Alle Rätsel sind von Anfang an sichtbar.
    - **GPX-Routen:** Unterstützt das Anzeigen von vordefinierten Routen aus `.gpx`-Dateien.
- **Vielseitige Rätsel:**
    - Multiple-Choice-Fragen mit direkter Rückmeldung.
    - Optionale Tipps und sofortige Auflösung.
    - Einbindung von Bildern pro Station.
- **Anpassbar & Erweiterbar:** Alle Touren, Rätsel und Texte werden über einfache `JSON`-Dateien konfiguriert.
- **Mehrsprachigkeit:** Das Design ist von Grund auf mehrsprachig und kann leicht um weitere Sprachen erweitert werden.
- **Datenschutzfreundlich:** Lädt Kartendaten direkt von den Anbietern (OSM/Esri). Es werden keine persönlichen Daten der Nutzer gespeichert.
- **Open Source:** Veröffentlicht unter der MIT-Lizenz.

---

## 🛠️ Technische Struktur

Das Projekt besteht aus einer PHP-Datei, die als "Konfigurations-Server" dient, und einer reinen JavaScript-Anwendung, die die gesamte Quizlogik ausführt.

1. **`index.php`**: Lädt die Hauptkonfiguration (`MapQuizzzes.json`), erkennt die Sprache und stellt die HTML-Grundstruktur sowie die Konfigurationsdaten für die JavaScript-App bereit. Dient auch als API-Endpunkt, um die Daten einer ausgewählten Tour (`quizdata.json`) zu laden.
2. **`MapQuizzzes.js`**: Das Herzstück der Anwendung. Es enthält die Klassen für:
    - **`App`**: Die Hauptklasse, die alles initialisiert.
    - **`QuizMap`**: Steuert die Leaflet-Karte, Marker, Routen und Steuerelemente.
    - **`TourManager`**: Verwaltet das Laden der Tourdaten, den Fortschritt des Spielers (gelöste Rätsel) und die Anzeige der Marker.
    - **`QuizModal`**: Steuert das Popup-Fenster für die Rätsel.
    - **`UIManager`**: Verwaltet den Startbildschirm und die allgemeine Benutzeroberfläche.
3. **Konfigurationsdateien (`.json`)**:
    - **`MapQuizzzes.json`**: Globale Konfiguration (Name, verfügbare Touren, UI-Übersetzungen).
    - **`quizdata.json`**: Enthält alle Rätselpunkte für eine bestimmte Tour (Koordinaten, Fragen, Antworten, Bilder).

---

## 🚀 Eigene Quiz-Tour erstellen

Um eine eigene Rätseltour zu erstellen, sind nur wenige Schritte nötig:

1. **Neuen Tour-Ordner erstellen:**
    - Erstellen Sie einen neuen Ordner (z. B. `/mein-neues-quiz/`).
    - Fügen Sie Ihre Bilder in Unterordner (`/img/` und `/min/` für Thumbnails) ein.

2. **`quizdata.json` anpassen:**
    - Erstellen Sie eine `quizdata.json`-Datei in Ihrem neuen Tour-Ordner.
    - Definieren Sie für jedes Bild einen Rätselpunkt mit `id` (Dateiname des Bildes), `title`, `question`, `answer` und den GPS-Koordinaten (`latitude`, `longitude`).

3. **`MapQuizzzes.json` aktualisieren:**
    - Fügen Sie den Namen Ihres neuen Ordners zur Liste `availableTours` hinzu.
    - Passen Sie bei Bedarf `quizName` und andere Texte an.

Fertig! Ihre neue Tour erscheint nun auf der Startseite zur Auswahl.

---

## 📄 Lizenz

Dieses Projekt steht unter der **MIT-Lizenz**. Die Lizenzdetails finden Sie in der `LICENSE.txt`-Datei.
