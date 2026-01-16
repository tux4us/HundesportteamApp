Hundesportteam App
<div align="center">
Bild anzeigen
Bild anzeigen
Bild anzeigen
Bild anzeigen
Bild anzeigen
Eine moderne Android App für den Hundesportverein Wiehl, die alle Inhalte der Website hundesportteam.de übersichtlich darstellt.
Features • Screenshots • Tech Stack • Installation • Datenschutz
</div>

📱 Features
Hauptfunktionen

📝 Vereinsblog: Alle Blog-Beiträge mit Bildern und vollständigem Inhalt
🏠 Vereinsseiten: Übersichtliche Darstellung aller Vereinsinformationen
💪 Trainingsbereich: Trainingsordnung und alle Unterseiten
📡 Offline-Modus: Automatisches Caching aller Inhalte für Offline-Nutzung
🌓 Dark Mode: Nahtloser Wechsel zwischen Hell- und Dunkelmodus
🔄 Pull-to-Refresh: Einfache Aktualisierung der Inhalte
🎨 Sportliches Design: Moderne UI in den Vereinsfarben Gold (#FFD48B) und Grün (#003A00)

Technische Features

Modern UI: Jetpack Compose mit Material Design 3
MVVM Architecture: Saubere Trennung von UI und Business Logic
WordPress Integration: Direkte Anbindung an WordPress REST API
Lokales Caching: Room Database für schnellen Offline-Zugriff
Dependency Injection: Hilt für modulare Architektur
Reactive Programming: Kotlin Coroutines und Flow
Image Loading: Coil mit intelligentem Caching


📸 Screenshots
BlogVereinsseitenTrainingDetail-AnsichtBild anzeigenBild anzeigenBild anzeigenBild anzeigen
Screenshots folgen

🛠 Tech Stack
Core

Language: Kotlin 1.9.20
UI Framework: Jetpack Compose (BOM 2024.01.00)
Architecture: MVVM (Model-View-ViewModel)
Dependency Injection: Hilt 2.50

Networking & Data

API Client: Retrofit 2.9.0 + OkHttp 4.12.0
Serialization: Kotlinx Serialization 1.6.2
RSS Parser: RssParser 6.0.4
Database: Room 2.6.1
Preferences: DataStore 1.0.0

UI & Media

Image Loading: Coil 2.5.0
HTML Parsing: Jsoup 1.17.2
Material Design: Material 3
Navigation: Navigation Compose 2.7.6

Build & Tools

Gradle: 8.2
Android Gradle Plugin: 8.2.1
Min SDK: 24 (Android 7.0)
Target SDK: 34 (Android 14)
Compile SDK: 34

📥 Installation
Voraussetzungen

Android Studio Hedgehog (2023.1.1) oder neuer
JDK 17
Android SDK 34
Internetverbindung für ersten Build

Setup-Schritte

Repository klonen

bash   git clone https://github.com/tux4us/hundesportteam-app.git
   cd hundesportteam-app

Projekt in Android Studio öffnen

   File → Open → Projekt-Ordner auswählen

Gradle Sync durchführen

Android Studio führt automatisch Gradle Sync durch
Dauer beim ersten Mal: 5-10 Minuten


App ausführen

Gerät/Emulator auswählen
Run ▶️ klicken



Manuelle Kommandozeile
bash# Dependencies laden
./gradlew build

# Debug APK erstellen
./gradlew assembleDebug

# Release APK erstellen (signiert)
./gradlew assembleRelease

🏗 Architektur
Projekt-Struktur
app/
├── data/
│   ├── local/          # Room Database, DAOs, Entities
│   ├── remote/         # API Services, DTOs
│   ├── repository/     # Repository Pattern
│   └── preferences/    # DataStore
├── di/                 # Hilt Modules
├── ui/
│   ├── blog/          # Blog Screen & ViewModel
│   ├── pages/         # Vereinsseiten Screen & ViewModel
│   ├── training/      # Training Screen & ViewModel
│   ├── detail/        # Detail Screen
│   ├── navigation/    # Navigation Setup
│   └── theme/         # Theme, Colors, Typography
└── util/              # Utilities
Datenfluss
WordPress API → Repository → ViewModel → UI
                    ↓
              Room Database
              (Offline Cache)

🔧 Konfiguration
API-Endpunkt
Die App verwendet die WordPress REST API von hundesportteam.de:
kotlin// di/AppModule.kt
private const val BASE_URL = "https://hundesportteam.de/"
Theme-Anpassung
Farben können in ui/theme/Color.kt angepasst werden:
kotlinval GoldLight = Color(0xFFFFD48B)
val DarkGreenLight = Color(0xFF003A00)

🚀 Build Variants
Debug Build
bash./gradlew assembleDebug

Debugging aktiviert
Logging aktiviert
Nicht optimiert

Release Build
bash./gradlew assembleRelease

ProGuard aktiviert
Optimiert
Signatur erforderlich

Signing Configuration
Für Release Builds erstellen Sie eine keystore.properties im Root-Verzeichnis:
propertiesstoreFile=/path/to/keystore.jks
storePassword=your_store_password
keyAlias=your_key_alias
keyPassword=your_key_password

🧪 Testing
bash# Unit Tests
./gradlew test

# Instrumentation Tests
./gradlew connectedAndroidTest

# Test Coverage
./gradlew jacocoTestReport

📄 Lizenz
© 2025 hundesportteamde. Alle Rechte vorbehalten.
Dieses Projekt ist proprietäre Software und nicht zur öffentlichen Nutzung oder Verbreitung gedacht. Die Nutzung, Vervielfältigung, Modifikation oder Weitergabe ist ohne ausdrückliche schriftliche Genehmigung des Hundesportteam Wiehl untersagt.
Einschränkungen

❌ Keine Nutzung ohne Genehmigung
❌ Keine Modifikation ohne Genehmigung
❌ Keine Verbreitung ohne Genehmigung
❌ Keine kommerzielle Nutzung

Für Lizenzanfragen kontaktieren Sie bitte: Kontakt über Website

🔒 Datenschutz
Datenschutzerklärung
Diese App respektiert Ihre Privatsphäre und hält sich an die DSGVO (Datenschutz-Grundverordnung).
1. Verantwortlicher
Hundesportteam Wiehl
Kontakt: Siehe hundesportteam.de
2. Datenerhebung und -verarbeitung
2.1 Automatisch erfasste Daten
Die App erfasst keine personenbezogenen Daten automatisch. Es werden keine Analyse-Tools, Tracking-Dienste oder Crash-Reporting-Tools verwendet.
2.2 Netzwerkverkehr
Die App kommuniziert ausschließlich mit:

hundesportteam.de - Zum Abrufen von Inhalten (Blog-Beiträge, Seiten, Bilder)

Art der übertragenen Daten:

HTTP-Requests an die WordPress REST API
Keine personenbezogenen Daten werden übertragen
Keine Authentifizierung erforderlich
Keine Cookies werden gesetzt

Technische Metadaten (serverseitig durch WordPress):

IP-Adresse (temporär, für technische Übertragung notwendig)
User-Agent (App-Identifikation)
Zeitstempel des Zugriffs

Diese Daten werden vom WordPress-Server verarbeitet und unterliegen der Datenschutzerklärung von hundesportteam.de.
2.3 Lokal gespeicherte Daten
Auf dem Gerät gespeichert:

Gecachte Inhalte (Blog-Beiträge, Seiten, Bilder) in der App-internen Room-Datenbank
Theme-Präferenz (Hell/Dunkel-Modus) im DataStore
Keine personenbezogenen Daten

Speicherort: App-interner Speicher (nicht von anderen Apps zugänglich)
Löschung: Alle Daten werden beim Deinstallieren der App automatisch gelöscht.
3. Zweck der Datenverarbeitung
Die App dient ausschließlich dem Zweck:

Darstellung von Vereinsinformationen
Offline-Verfügbarkeit von Inhalten
Verbesserung der Benutzererfahrung durch Caching

4. Rechtsgrundlage
Die Datenverarbeitung erfolgt auf Grundlage von:

Art. 6 Abs. 1 lit. f DSGVO (Berechtigtes Interesse): Bereitstellung der App-Funktionalität
Art. 6 Abs. 1 lit. a DSGVO (Einwilligung): Bei freiwilliger Nutzung der App

5. Datenweitergabe

✅ Keine Weitergabe an Dritte
✅ Keine Verkauf von Daten
✅ Keine Werbenetzwerke
✅ Keine Analytics-Dienste
✅ Keine Social Media Integration

6. Berechtigungen
Die App benötigt folgende Android-Berechtigungen:
BerechtigungZweckErforderlichINTERNETLaden von Inhalten von hundesportteam.deJaACCESS_NETWORK_STATEPrüfung der InternetverbindungJa
Keine weiteren Berechtigungen werden angefragt.
7. Datensicherheit
Technische Maßnahmen:

HTTPS-Verschlüsselung für alle Netzwerkverbindungen
App-interner Speicher (sandboxed, kein Zugriff durch andere Apps)
Keine Speicherung sensibler Daten
Regelmäßige Sicherheitsupdates

8. Speicherdauer

Gecachte Inhalte: Bis zur Deinstallation der App oder manueller Löschung
Präferenzen: Bis zur Deinstallation der App
Server-Logs: Siehe Datenschutzerklärung von hundesportteam.de

9. Ihre Rechte (DSGVO)
Sie haben folgende Rechte:

Art. 15 DSGVO: Auskunft über Ihre gespeicherten Daten
Art. 16 DSGVO: Berichtigung unrichtiger Daten
Art. 17 DSGVO: Löschung Ihrer Daten ("Recht auf Vergessenwerden")
Art. 18 DSGVO: Einschränkung der Verarbeitung
Art. 20 DSGVO: Datenübertragbarkeit
Art. 21 DSGVO: Widerspruch gegen die Verarbeitung
Art. 77 DSGVO: Beschwerde bei einer Aufsichtsbehörde

Ausübung Ihrer Rechte:
Da die App keine personenbezogenen Daten sammelt oder speichert, gibt es praktisch keine zu löschenden oder zu exportierenden Daten.
Für Anfragen bezüglich serverseitiger Daten (WordPress-Logs) kontaktieren Sie bitte direkt: Kontakt über hundesportteam.de
10. Daten löschen
App-Daten löschen:
Android: Einstellungen → Apps → Hundesportteam → Speicher → Daten löschen
App deinstallieren:

Alle lokalen Daten werden automatisch gelöscht
Keine Daten verbleiben auf dem Gerät

11. Änderungen dieser Datenschutzerklärung
Wir behalten uns vor, diese Datenschutzerklärung zu aktualisieren, um Änderungen in der App oder rechtlichen Anforderungen Rechnung zu tragen.
Stand: Januar 2025
Version: 1.0
12. Kontakt
Bei Fragen zum Datenschutz kontaktieren Sie bitte:
Hundesportteam Wiehl
Website: hundesportteam.de
E-Mail: Siehe Kontaktformular auf der Website
13. Aufsichtsbehörde
Sie haben das Recht, Beschwerde bei einer Datenschutz-Aufsichtsbehörde einzulegen:
Landesbeauftragte für Datenschutz und Informationsfreiheit Nordrhein-Westfalen
Kavalleriestraße 2-4
40213 Düsseldorf
Telefon: 0211/38424-0
E-Mail: poststelle@ldi.nrw.de

🤝 Beitragen
Da dies ein proprietäres Projekt ist, werden externe Beiträge derzeit nicht akzeptiert.
Für Fehlerberichte oder Feature-Anfragen wenden Sie sich bitte an den Vereinsvorstand.

📞 Kontakt & Support

Website: hundesportteam.de
Technische Fragen: Siehe Kontaktformular auf der Website
Bug Reports: Issues (falls aktiviert)


🙏 Danksagungen

WordPress Team - Für die hervorragende REST API
Android Team - Für Jetpack Compose
JetBrains - Für Kotlin
Open Source Community - Für die genutzten Bibliotheken


📚 Weitere Dokumentation

Installation Guide
Troubleshooting
Quick Start
Final Configuration


<div align="center">
Made with ❤️ for Hundesportteam.de
🐕 Hundesport • 🏃 Training • 🏆 Wettkämpfe
</div>
