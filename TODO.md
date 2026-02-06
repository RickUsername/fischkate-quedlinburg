# Fischkate Website - Offene Punkte & TODOs

> **Letztes Update:** 06.02.2026
> **Aktuelle Version:** V.0.1.0

---

## 🚨 KRITISCH - Ohne diese Fixes kann die Seite nicht live gehen

### 1. Formspree Formulare ✅

**Status:** ✅ **ERLEDIGT** (06.02.2026)

Formspree-Endpoints eingetragen: Bewerbungen (xeeljdkw), Reservierungen (xlgwrvna). Simulations-Alert entfernt, echtes Absenden aktiviert.

---

## 🔴 HOCH - Muss vor Go-Live erledigt werden

### 2. Tailwind CSS - Entwicklungsversion ersetzen ✅

**Status:** ✅ **ERLEDIGT** (05.02.2026)

Tailwind v4.1.18 lokal kompiliert. CDN-Script durch minifizierte tailwind.css (45 KB) ersetzt. Nur genutzte Klassen enthalten. Zum Neu-Kompilieren: `npx @tailwindcss/cli --input input.css --output tailwind.css --minify`

### 3. Video komprimiert ✅

**Status:** ✅ **ERLEDIGT** (05.02.2026)

VideoBrotSchneiden.mp4 von 138 MB auf 5,2 MB komprimiert (CRF 18, 1080p, ffmpeg). Original-Backup liegt in Fischkate\VideoBrotSchneiden_BACKUP.mp4.

---

## 🟡 MITTEL - Sollte vor oder kurz nach Launch gemacht werden

### 4. Echtes Favicon erstellen ✅

**Status:** ✅ **ERLEDIGT** (05.02.2026)

Favicon aus Ankersymbol.png (Inkscape) erstellt. Dunkelblau (#1e3a8a) mit transparentem Hintergrund. Dateien: favicon.ico, favicon-16.png, favicon-32.png, apple-touch-icon.png. HTML-Tags in index.html bereits eingetragen.

### 5. Datenschutzerklaerung: Formspree erwaehnen ✅

**Status:** ✅ **ERLEDIGT** (06.02.2026)

Formspree als Auftragsverarbeiter in Datenschutzerklaerung ergaenzt (Punkt 2b + 3). Google Fonts und Tailwind CDN Eintraege entfernt (werden jetzt lokal gehostet).

---

## 🟢 NIEDRIG / OPTIONAL - Nice to have

### 14. Canonical-Tag fuer SEO ✅

**Status:** ✅ **ERLEDIGT** (06.02.2026)

Canonical-Tag auf fischkate-harz.de gesetzt. Alle URLs aktualisiert.

### 15. AI-Agent / Schema.org Optimierung ✅

**Status:** ✅ **ERLEDIGT** (06.02.2026)

Schema.org erweitert: Geo-Koordinaten, servesCuisine, potentialAction (ReserveAction + ApplyAction), Menu-URL, description. Alte Meta-Tags durch robots + description:actions ersetzt. Anker #reservierung hinzugefuegt.

### 16. Google Bewertungen Integration

**Status:** 🟢 **OPTIONAL**

Google Review Widget einbinden, mehr Bewertungen anzeigen, Link zu Google Business Profil.

### 17. PDF-Speisekarte Integration

**Status:** 🟢 **OPTIONAL**

Download-Link zur PDF-Speisekarte hinzufuegen. Datei vorhanden: `SPEISENKARTE.10.01.2026.pdf`

### 18. Analytics & Tracking

**Status:** 🟢 **OPTIONAL**

Google Analytics oder datenschutzfreundliche Alternative (z.B. Plausible, Umami) einbinden.

---

## ✅ ERLEDIGT

### Speisekarte & Allergene
- ✅ Vollstaendige Speisekarte mit allen Kategorien
- ✅ Vollstaendige Getraenkekarte
- ✅ Allergene & Zusatzstoffe Listen komplett
- ✅ E407 (Carrageen) bei Forellenfilet und Raeucherfisch-Trilogie ergaenzt (05.02.2026)
- ✅ E407 in Zusatzstofftabelle und allergenLabels aufgenommen (05.02.2026)
- ✅ "Kleines Seelachs filet" Tippfehler korrigiert (05.02.2026)
- ✅ Linsenbratlinge: Falsche Allergen-Anzeige im Modal behoben (05.02.2026)
- ✅ Allergen-Korrekturen laut Original-Speisekarte (Januar 2026)

### Rechtliches & Kontakt
- ✅ Email-Adresse (Fisch-Kate-qlb@gmx.de) in Datenschutz und Impressum
- ✅ Impressum vollstaendig (USt-IdNr. nicht erforderlich - geprueft)
- ✅ Datenschutzerklaerung grundsaetzlich vorhanden
- ✅ Social Media Links (Facebook + Instagram) eingetragen
- ✅ Oeffnungszeiten korrekt (Di-Sa 10-21h)

### Technik & Design
- ✅ Responsive Design (Mobile, Tablet, Desktop)
- ✅ Mobile Navigation
- ✅ Mediathek mit Lightbox
- ✅ Videos eingebunden
- ✅ SEO-Grundlagen (Meta-Tags, Structured Data)
- ✅ Cookie-Banner mit LocalStorage-Persistenz
- ✅ Navigation zu Allergenen im Footer
- ✅ Weihnachts-Easteregg deaktiviert (fuer naechste Saison vorbereitet)
- ✅ Reservierungshinweis ("wird erst nach Bestaetigung gueltig")
- ✅ Allergene werden im Dish-Info-Modal korrekt angezeigt
- ✅ Google Maps nur verlinkt, nicht eingebettet (DSGVO-konform)
- ✅ Kein Tracking/Analytics eingebunden (DSGVO-freundlich)

### Go-Live Fixes (05.02.2026)
- ✅ Unsplash-Fallback-Bilder entfernt (3 Stellen) - keine externen Bildverbindungen mehr
- ✅ Schema.org-Bild gefixt (IMG-20251124-WA0006.jpg -> TerasseJanaBlumen.jpg)
- ✅ Lucide Icons auf feste Version 0.563.0 gepinnt
- ✅ Versionsnummer aus Title-Tag entfernt
- ✅ og:image auf absolute URL gesetzt
- ✅ Copyright-Jahr auf 2026 aktualisiert
- ✅ Google Fonts lokal gehostet (fonts/ Ordner, keine Google-Verbindung mehr)
- ✅ Cookie-Banner mit "Nur notwendige" / "Alles akzeptieren" Buttons (DSGVO-konform)
- ✅ Google-Bewertung: Dummy durch echtes Zitat von Matthias E. ersetzt
- ✅ Video komprimiert: 138 MB -> 5,2 MB (CRF 18, 1080p, ffmpeg)
- ✅ Favicon erstellt: Anker-Symbol in Dunkelblau mit transparentem Hintergrund (favicon.ico, favicon-16/32.png, apple-touch-icon.png)
- ✅ Tailwind CSS: CDN-Dev-Script durch lokal kompilierte tailwind.css (45 KB, minifiziert) ersetzt
- ✅ Formspree eingerichtet: Bewerbungen (xeeljdkw) + Reservierungen (xlgwrvna), Simulation entfernt
- ✅ Datenschutzerklaerung aktualisiert: Formspree ergaenzt, Google Fonts + Tailwind CDN Eintraege entfernt
- ✅ Datenschutzerklaerung komplett erweitert (8 Abschnitte, DSGVO-konform, Betroffenenrechte, Aufsichtsbehoerde)
- ✅ Datenschutz-Checkbox bei beiden Formularen (Pflichtfeld mit USA-Hinweis)
- ✅ Cookie-Einstellungen Link im Footer (zum erneuten Anzeigen des Banners)
- ✅ Uhrzeitfeld Reservierung: Keine Blockade mehr, nur noch Warnung bei Zeiten ausserhalb 10-21 Uhr
- ✅ Canonical-Tag auf fischkate-harz.de, alle URLs aktualisiert
- ✅ Schema.org erweitert: Geo, Actions, Menu-URL, servesCuisine, Anker #reservierung

---

## 📋 Empfohlene Reihenfolge fuer die Umsetzung

### Phase 1: Kritische Fixes (VOR Launch)
1. Formspree einrichten (#1)
2. Tailwind fuer Produktion kompilieren (#2)
3. Video komprimieren (#3)

### Phase 2: Feinschliff (VOR oder kurz NACH Launch)
4. Favicon erstellen (#4)
5. Datenschutz um Formspree ergaenzen (#5)

### Phase 3: Launch
- Auf Webserver hochladen
- Domain konfigurieren
- SSL-Zertifikat pruefen
- Alle Formulare live testen
- Google Search Console einrichten

---

## 📊 Versions-Historie

| Version | Datum | Aenderungen |
|---------|-------|-------------|
| V.0.1.1 | 05.02.2026 | Go-Live Fixes: Fonts lokal, Unsplash weg, Cookie-Banner, SEO-Fixes |
| V.0.1.0 | 05.02.2026 | E407 ergaenzt, Seelachsfilet-Typo, Linsenbratlinge-Allergene gefixt |
| V.0.0.7 | 11.01.2026 | Allergen-Korrekturen laut Original-Speisekarte |
| V.0.0.6 | 11.01.2026 | Reservierungshinweis + Weihnachts-Easteregg deaktiviert |
| V.0.0.5 | 10.01.2026 | Social Media, Email, Oeffnungszeiten finalisiert |
| V.0.0.4 | - | Rechtliche Texte wiederhergestellt |
| V.0.0.3 | - | Basis-Website |

---

**Zuletzt aktualisiert:** 05.02.2026
