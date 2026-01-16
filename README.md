Hundesportteam Android App
Eine native Android-App für den Hundesportverein, die alle Inhalte der WordPress-Website https://hundesportteam.de/ übersichtlich darstellt.
Features
✨ Hauptfunktionen
•
Blog-Beiträge: Alle Vereins-Blog-Beiträge in einer übersichtlichen Liste
•
Vereinsseiten: Alle wichtigen Seiten des Vereins (außer Prüfungsordnung)
•
Trainingsseiten: Trainingsordnung und alle Unterseiten
•
Offline-Verfügbarkeit: Alle Inhalte werden lokal gecacht
•
Hell/Dunkel-Modus: Automatischer Wechsel zwischen Hell- und Dunkelmodus
•
Sportliches Design: Ansprechende Gestaltung in den Vereinsfarben Gold (#FFD48B) und Dunkelgrün (#003A00)
🏗️ Technische Features
•
WordPress REST API Integration: Dynamischer Abruf aller Inhalte
•
Room Database: Lokales Caching für Offline-Nutzung
•
Jetpack Compose: Moderne, deklarative UI
•
MVVM Architektur: Saubere Code-Struktur
•
Hilt Dependency Injection: Modulare Dependency-Verwaltung
•
Coil: Effizientes Laden und Caching von Bildern
•
Material Design 3: Zeitgemäßes Design-System
Technologie-Stack
•
Sprache: Kotlin
•
UI Framework: Jetpack Compose
•
Architektur: MVVM (Model-View-ViewModel)
•
Dependency Injection: Hilt
•
Netzwerk: Retrofit + OkHttp
•
Datenbank: Room
•
Serialization: Kotlinx Serialization
•
Bild-Loading: Coil
•
RSS Parsing: RssParser
•
HTML Parsing: Jsoup
•
Navigation: Jetpack Navigation Compose
Projekt-Struktur
app/
├── data/
│   ├── local/
│   │   ├── dao/           # Database Access Objects
│   │   ├── entity/        # Room Entities
│   │   └── AppDatabase    # Room Database
│   ├── model/             # Data Models
│   ├── preferences/       # DataStore Preferences
│   ├── remote/            # API Services
│   └── repository/        # Repositories (Data Layer)
├── di/                    # Dependency Injection Modules
├── ui/
│   ├── blog/             # Blog-Screen & ViewModel
│   ├── detail/           # Detail-Screen
│   ├── navigation/       # Navigation Setup
│   ├── pages/            # Vereinsseiten-Screen & ViewModel
│   ├── theme/            # Theme, Colors, Typography
│   └── training/         # Training-Screen & ViewModel
└── util/                 # Utility Classes

Installation & Build
Voraussetzungen
•
Android Studio Hedgehog (2023.1.1) oder neuer
•
JDK 17
•
Android SDK API 34
•
Gradle 8.2+
Build-Anleitung
1.
Projekt in Android Studio öffnen
File -> Open -> Projekt-Ordner auswählen
2.
Gradle Sync durchführen
File -> Sync Project with Gradle Files
3.
App builden und ausführen
•
Debug Build: Run -> Run 'app'
•
Release Build: Build -> Generate Signed Bundle / APK
Konfiguration
Die App ist vorkonfiguriert für:
•
Base URL: https://hundesportteam.de/
•
WordPress REST API Endpunkt: /wp-json/wp/v2/
•
Minimale Android Version: API 24 (Android 7.0)
•
Ziel Android Version: API 34 (Android 14)
App-Struktur
Navigation
Die App verwendet eine Bottom Navigation Bar mit drei Hauptbereichen:
1.
Blog 📝 - Vereinsblog-Beiträge
2.
Verein 🏠 - Vereinsseiten
3.
Training 💪 - Trainingsseiten
Datenfluss
WordPress API -> Repository -> ViewModel -> UI Screen
                    ↓
              Room Database (Cache)
Offline-Funktionalität
•
Beim ersten Start werden alle Daten von der API geladen
•
Daten werden in der lokalen Room-Datenbank gespeichert
•
Bei erneutem Öffnen werden gecachte Daten sofort angezeigt
•
Aktualisierung über Pull-to-Refresh oder Refresh-Button
Design-System
Farbschema
Light Mode:
•
Primary: Gold (#FFD48B)
•
Secondary: Dunkelgrün (#003A00)
•
Background: Cremefarben (#FFFBF5)
•
Surface: Weiß (#FFFFFF)
Dark Mode:
•
Primary: Gold (#FFD48B)
•
Secondary: Hellgrün (#005500)
•
Background: Dunkelgrau (#1A1C1A)
•
Surface: Grau (#2D2F2D)
Typografie
•
Schriftfamilie: System Default (Roboto auf den meisten Android-Geräten)
•
Headlines: Bold
•
Titles: SemiBold/Medium
•
Body: Normal
API-Endpunkte
Die App nutzt folgende WordPress REST API Endpunkte:
GET /wp-json/wp/v2/posts       # Blog-Beiträge
GET /wp-json/wp/v2/posts/{id}  # Einzelner Blog-Beitrag
GET /wp-json/wp/v2/pages       # Seiten
GET /wp-json/wp/v2/pages/{id}  # Einzelne Seite
Parameter:
•
per_page: Anzahl der Ergebnisse (Standard: 100)
•
_embed: Einbetten von Medien (immer true)
•
orderby: Sortierung (date, menu_order)
•
order: Reihenfolge (asc, desc)
Zukünftige Erweiterungen
Mögliche Features für zukünftige Versionen:
•
[ ] Push-Benachrichtigungen für neue Blog-Beiträge
•
[ ] Favoriten-Funktion
•
[ ] Teilen-Funktionalität
•
[ ] Suchfunktion
•
[ ] Kommentar-Funktion
•
[ ] Event-Kalender
•
[ ] Mitgliederbereich
Bekannte Einschränkungen
•
Die App benötigt eine Internetverbindung für den ersten Datenabr uf
•
Sehr große Bilder können die Ladezeit beeinflussen
•
Die Darstellung von komplexen WordPress-Shortcodes ist limitiert
Lizenz
© 2025 Hundesportteam. Alle Rechte vorbehalten.
Support
Bei Fragen oder Problemen:
•
Website: https://hundesportteam.de/
•
E-Mail: [hundesportteam@online.de]
Changelog
Version 1.0.0 (Initial Release)
•
Implementierung aller Grundfunktionen
•
Blog, Vereinsseiten und Trainingsseiten
•
Offline-Caching
•
Hell/Dunkel-Modus
•
Sportliches Design
