# STAFAM DESIGN.md – Google Stitch Master Design Reference

## 0. Aufgabe, Geltungsbereich und Priorität

Designsystem für die **öffentliche STAFAM Website** und den geschützten Bereich **Digitale Services**, desktop-first und mobile-first mit derselben Design-DNA. **STAFAM Manage** ist ein separates Administrationsprodukt und darf nicht in diesen Stilauftrag aufgenommen werden.

Prioritäten bei Widersprüchen:
1. Vom Auftraggeber ausdrücklich **visuell genehmigte Auth-V4** und hochgeladene Original-Referenzbilder
2. Dieses `DESIGN.md`
3. `tokens/brand.json` und originale Logo-Datei in `assets/`
4. Neuer Gestaltungsentwurf für bisher noch nicht freigegebene Bereiche

**WICHTIG:** Neues Design nicht aus älteren Stitch-Outputs extrapolieren. Logo, Navigation, Icons, Schrift und Komponenten nicht bei jedem Screen neu erfinden.

## 1. Markenidentität [BESCHLOSSEN]

- Name: STAFAM
- Offizielle Wort-Bild-Marke: `assets/stafam-logo-original-embedded.svg`; als unveränderte Grafik verwenden, **nicht nachzeichnen**, keine zusätzlichen Wörter neben dem Logo anbringen.
- Schriftfamilie überall: **Roboto Condensed**, `font-family: "Roboto Condensed", sans-serif;`. Keine Archivo Narrow, Inter, Roboto (ohne Condensed) oder systemeigene Ersatzschrift als Designauswahl.
- Primärblau: **#13416D**
- Markengrün: **#00A087**
- Hellblau: **#36A4DD**
- Kontrast: für grünen Text bei Bedarf dunklere funktionsbezogene Variante `#006E5D`; weiße Texte auf `#00A087` nicht ungeprüft einsetzen.
- Medizinische Programmkategorien (exakte unveränderliche Farben):
  - Vorträge Ärztinnen/Ärzte: **#1D9BD6**
  - Seminare Ärztinnen/Ärzte: **#0A987F**
  - Vorträge medizinisches Personal: **#E56A0B**
  - Seminare medizinisches Personal: **#6A4E76**
  - Kombiseminare: **#B81818**

## 2. Gestaltungsprinzipien

Sachlich, hochwertig, professionell, lesbar, medizinischer Fortbildung angemessen; luftig, helle Flächen, klares Navy, dezente grüne und hellblaue Akzente. Keine überladenen Dashboards, keine ungewöhnlichen Sidebar-Navigationsvarianten, keine dekorativen Fantasie-Icons.

Visuelle Basis der genehmigten Auth V4: Desktop weißer ca. 72 px Header, max. Contentbreite ca. 1280 px; mobile Header ca. 60 px, horizontale Paddingbereiche ca. 16 px; Mobile-Bottom-Nav ca. 64 px plus Safe-Area. Diese Maße sind visuelle Referenzen, keine technische Freigabe anderer Breakpoints.

Buttons etwa 8 px Radius, normale Karten etwa 12 px, große Hero-Flächen etwa 16 px. Richtwerte statt ungetesteter Design-Zwang für jedes neue Element. Buttons ca. 44 px Standardhöhe; klarer Fokus, ausreichend Touch-Flächen.

Alle Icons als echte, einfache **inline SVG** mit verständlicher Symbolik, keine Ligaturtexte wie `keyboard_arrow_down`, `menu`, `notifications`, `video_library` usw. Auch bei fehlender externer Icon-Font müssen Icons korrekt sichtbar sein.

## 3. Desktop: globaler Header [VISUELL FREIGEGEBEN]

Logo **allein links**. Hauptnavigation exakt in dieser Reihenfolge:
**Home | Über uns ▼ | Kongress ▼ | Digitale Services ▼ | Mitgliedschaft ▼ | News ▼ | Services ▼**

Rechts Such-Icon und Kontobereich. Das Account-Dropdown zeigt in Design-Demos eine **ausdrücklich gekennzeichnete Mockidentität**; reale Daten später ausschließlich aus authentifizierter Session. Dropdowns öffnen beim **ersten Klick**, bleiben stabil und schließen durch zweiten Klick, Klick außerhalb oder Escape. Alle Einträge sind als einzeln klickbare Zeilen, nie ineinanderfließender Text, darzustellen.

**Profilmenü in dieser Reihenfolge:**
1. Übersicht / Mein Bereich
2. Meine Kongresse
3. Mediathek & Archiv
4. Webinare & Fortbildungen
5. Meine Dokumente & Nachweise
6. Mein Profil & Stammdaten
7. Abmelden

Die genaue produktive URL-Zuordnung ist **nicht** Teil dieses Designauftrags. Keine erfundenen Routen oder unsichere Logout-GET-Aktion.

## 4. Mobile: globaler Header, Drawer, Bottom Navigation [VISUELL FREIGEGEBEN]

- Oben: links 44×44 Hamburger, Original-STAFAM-Logo **zentriert**, rechts Benachrichtigungs-SVG und Profil-Avatar.
- Hamburger-Menü: Menüeinträge und **aufklappbare echte Untermenüs** in der Hierarchie der Desktop-Hauptnavigation; nicht einfach alte Desktopleiste untereinander kopieren.
- **Unten im Hamburger-Menü, oberhalb der Aktionsbuttons:** eigener Kongressblock:
  **56. Kongress für Allgemeinmedizin 2026**, **26.–28. November 2026**, **Stadthalle Graz**.
- Ganz unten zwei klar erkennbare Buttons: **Login** und **Anmelden**.
- **Unabhängig vom Hamburger-Menü** gibt es eine dauerhaft sichtbare, feste Mobile-Bottom-Navigation mit fünf Einträgen: **Übersicht | Live | Mediathek | Programm | Bereich**.
- Safe-Area-Abstand, keine verdeckten Inhalte, kein horizontaler Scroll. Bottom-Navigation nur bei geeigneten mobilen Breakpoints; über Live-Berechtigungen entscheidet erst das Backend.
- Mobiles Profilmenü muss ebenfalls vollständig geöffnet und getestet werden können; keine abgeschnittenen oder nebeneinanderlaufenden Einträge.

## 5. Auth-Seite [VISUELL FREIGEGEN – AUSGANGSBASIS]

**Login, Registrierung und Kennwort vergessen sind Ansichten auf derselben Seite**, erreichbar per Tabs/Wechsel ohne Navigationsbruch. Professioneller zweispaltiger Desktop-Aufbau: links Informations-/Hero-Bereich in Navy, rechts Formular; mobile Ansicht responsiv. Die Referenz V4 enthält funktionsfähige Demo-Formulare ohne echtes Backend. Alle drei Ansichten müssen vorzeigbar sein.

Keine tatsächliche Kontenerstellung, Passwortänderung, E-Mail-Übermittlung oder Berechtigungsvergabe im Prototyp behaupten. Produktive OIDC/PKCE-Integration wird unabhängig davon geprüft.

## 6. Digitale Services: fachliche Informationsarchitektur [BESCHLOSSEN]

Kontextnavigation:
- **Übersicht**
- **Kongresse** (mit **Kongressjahr-Auswahl**)
  - Mein Programm
  - Live-Stream
  - Seminare
  - Mediathek
- **Webinare** (kongressjahrunabhängig)
- **Dokumente** (kongressbezogene und kongressunabhängige)
- **Mein Profil**

Diese Informationsarchitektur **nicht** als zweite, stets wiederholte globale Kopf-Navigation oder als alte permanente linke Sidebar erzwingen. Kontextnavigation darf auf passende und später zu prüfende Weise integriert werden. Die globale genehmigte V4-Navigation ist unveränderlich.

## 7. Weitere Screen-Anforderungen – Design noch OFFEN

### Kongresse und Programm
Kongressübersicht mit Jahreswahl; persönliche Vorträge/Seminare, Detailansichten, Zugangssituationen, leere und gesperrte Zustände. Publikum Ärzte/medizinisches Personal als exklusive fachliche Programmsichten (Ärzte als Standard, vorbehaltlich späterer Produktprüfung). Nur die fünf fixierten Farbkategorien verwenden. Live nur für Kongressjahre, in denen angeboten, mit klaren Zugangsrechten.

### Webinare
Jahresunabhängige Übersicht, Reihen, Einzelwebinare, Detailseite, Anmeldung; Ärzte, medizinisches Personal oder beide als Zielgruppe. Teilnahme **online, vor Ort oder hybrid** je Angebot; nach Anmeldung Wechsel Online ↔ Vor Ort möglich, ohne Dublette. Meine Anmeldungen, Erinnerungen, optionale Multiple-Choice-Wissensüberprüfung, Anwesenheits- und Fortbildungsnachweise; CME-/DFP-Buchung nur nach tatsächlicher backendseitiger Freigabe. Historische To-Go-Materialien berücksichtigen, ohne Titel/Inhalte zu erfinden.

### Mediathek
Kongressjahr und Berechtigungen, Aufzeichnungen/Hauptvorträge, ggf. separat gekaufte Aufzeichnungsrechte; geeignete Kennzeichnung von gesponserten Inhalten. Aufzeichnung allein bedeutet nicht Livestreamzugriff.

### Dokumente
Zertifikate, Seminar-/Webinarbestätigungen, Rechnungen und Nachweise. Kongressbezogene **und** vom Kongressjahr unabhängige Dokumente, mit sinnvollen Filtern.

### Profil
Persönliche Stammdaten, geschützte Zustände, keine Erfindung tatsächlich gespeicherter Teilnehmerdaten.

## 8. Testzustände

Mindestens: Desktop geschlossenes Hauptmenü, geöffnetes Haupt-Dropdown, geöffnetes Profil-Dropdown; mobil Header, geöffneter Hamburger-Drawer mit Kongressblock und Login/Anmelden, geöffnetes Untermenü, geöffnetes Profilmenü, sichtbare Bottom-Navigation; Auth-Tabs Login/Registrierung/Kennwort vergessen. Bei künftigen Screens zusätzlich: geladen, leer, gesperrt, Fehlermeldung, Tablet/Smartphone.

## 9. Generierungsregeln

- Bei **jeder** Seite dieselbe Logo-Datei und Header-/Nav-Komponenten wiederverwenden.
- Keinerlei freie Neuerfindung der Navigation.
- Keine Fantasie-Daten, -Berechtigungen, -DFP-Zahlen, -Live-Verfügbarkeit, -Webinar-Termine, -Namen oder -Routen als reale Fakten.
- Mockinhalte eindeutig mit **DEMO** kennzeichnen.
- Entwurfsstatus benennen: **[BESCHLOSSEN]**, **[VISUELL FREIGEGEBEN]**, **[OFFEN]**, **[IDEE]**.
- Keine Umsetzung von STAFAM Manage.
- Erst Master-Komponentenboard zur visuellen Freigabe. **Nicht** sofort massenhaft alle Screens generieren.
- Dieses Dokument spezifiziert das Design. Es ist **keine** Freigabe für tatsächliche Frontend-, Identity-, Zahlungs-, Teilnehmer- oder Deploy-Änderungen.
