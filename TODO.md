# Fischkate Website - Offene Punkte & TODOs

> **Letztes Update:** 05.02.2026
> **Aktuelle Version:** V.0.1.0

---

## 🚨 KRITISCH - Ohne diese Fixes kann die Seite nicht live gehen

### 1. Formspree Formulare (2x PLACEHOLDER)

**Status:** ⚠️ **OFFEN**

**Problem:** Beide Formulare nutzen `action="https://formspree.io/f/PLACEHOLDER"` - Daten gehen ins Nichts.

**Betrifft:**
- Bewerbungsformular (Zeile ~1742)
- Reservierungsformular (Zeile ~1890)

**Zusatzproblem Bewerbung:** Die `sendApplication()`-Funktion ruft `e.preventDefault()` auf und zeigt nur einen `alert("Simulation: ...")`. Selbst mit korrektem Endpunkt wuerden keine Daten gesendet. Der Alert und das preventDefault muessen entfernt/angepasst werden.

**Loesung:**
1. Formspree-Account erstellen auf https://formspree.io
2. Zwei Formulare anlegen ("Bewerbungen" + "Tischreservierungen")
3. Die generierten Form-IDs in `index.html` eintragen
4. Simulation-Alert im JavaScript entfernen
5. Formulare testen

---

## 🔴 HOCH - Muss vor Go-Live erledigt werden

### 2. Unsplash-Fallback-Bilder entfernen

**Status:** ⚠️ **OFFEN**

**Problem:** An 3 Stellen werden bei fehlenden Bildern externe Unsplash-Stock-Fotos geladen. DSGVO-problematisch (Datenverbindung zu externem Server ohne Einwilligung) und unprofessionell.

**Betroffene Stellen:**
- Zeile ~189: Hero-Video-Fallback
- Zeile ~1610: StolzEingang.jpg Fallback
- Zeile ~1616: JanaAmRotenFass.jpg Fallback

**Loesung:** `onerror="this.src='https://images.unsplash.com/...'"` entfernen. Alle lokalen Bilder existieren und funktionieren.

### 3. Fehlendes Bild in Schema.org

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~68: `"image": "IMG-20251124-WA0006.jpg"` - Diese Datei existiert NICHT im Verzeichnis. Google bekommt ein kaputtes Bild fuer Rich Snippets.

**Loesung:** Pfad auf ein vorhandenes Bild aendern (z.B. `TerasseJanaBlumen.jpg`) oder die Datei hinzufuegen.

### 4. Tailwind CSS - Entwicklungsversion ersetzen

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~27: `<script src="https://cdn.tailwindcss.com"></script>` ist die **Dev-CDN-Version**. Laut Tailwind-Docs nicht fuer Produktion geeignet - langsam, laedt unnoetig viel JS, kann sich jederzeit aendern.

**Loesung:** Tailwind als Build-Step kompilieren oder eine feste, minifizierte CSS-Datei generieren.

### 5. Lucide Icons - Version nicht fixiert

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~28: `<script src="https://unpkg.com/lucide@latest"></script>` - `@latest` kann sich jederzeit aendern. Icons koennten ploetzlich anders aussehen oder fehlen.

**Loesung:** Feste Version pinnen, z.B. `lucide@0.263.1`.

### 6. Video viel zu gross (144 MB)

**Status:** ⚠️ **OFFEN**

**Problem:** `VideoBrotSchneiden.mp4` ist 144 MB. Das belastet die Ladezeit extrem.

**Loesung:** Video auf 10-20 MB komprimieren (z.B. mit HandBrake, niedrigere Aufloesung/Bitrate).

---

## 🟡 MITTEL - Sollte vor oder kurz nach Launch gemacht werden

### 7. Versionsnummer aus Title-Tag entfernen

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~7: `<title>Fischkate Quedlinburg - V.0.1.0</title>` - erscheint so in Google-Suchergebnissen.

**Loesung:** Aendern zu z.B. `Fischkate Quedlinburg - Frischer Fisch im Herzen des Harzes`

### 8. og:image braucht absolute URL

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~19: `<meta property="og:image" content="TerasseJanaBlumen.jpg">` - Social-Media-Vorschaubilder funktionieren nur mit vollstaendiger URL.

**Loesung:** Aendern zu `https://www.fischkate-quedlinburg.de/TerasseJanaBlumen.jpg`

### 9. Echtes Favicon erstellen

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~23: Favicon ist ein Inline-SVG mit Anker-Emoji. Funktioniert, sieht aber unprofessionell aus in Browser-Tabs und Lesezeichen.

**Loesung:** Richtiges `.ico` oder `.png` Favicon erstellen (z.B. aus dem Logo).

### 10. Copyright-Jahr aktualisieren

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~1949: `Copyright 2025` - muss auf 2026 aktualisiert werden.

### 11. Cookie-Banner - Ablehnen-Option fehlt

**Status:** ⚠️ **OFFEN**

**Problem:** Der Banner bietet nur "Alles klar". DSGVO verlangt eine echte Wahlmoeglichkeit, besonders wegen Google Fonts (externe Datenverbindung).

**Loesung:** "Ablehnen"-Button hinzufuegen. Bei Ablehnung: Google Fonts nicht laden (lokal gehostete Fonts als Fallback).

### 12. Google Fonts lokal hosten (DSGVO)

**Status:** ⚠️ **OFFEN**

**Problem:** Zeile ~40: Fonts werden von Google-Servern geladen. Es gab bereits Abmahnwellen wegen Google Fonts und DSGVO.

**Loesung:** Fonts herunterladen und lokal einbinden. Dann entfaellt auch das DSGVO-Problem im Cookie-Banner.

### 13. Datenschutzerklaerung: Formspree erwaehnen

**Status:** ⚠️ **OFFEN**

**Problem:** Wenn Formulardaten ueber Formspree (US-Dienst) laufen, muss das in der Datenschutzerklaerung erwaehnt werden inkl. Rechtsgrundlage.

---

## 🟢 NIEDRIG / OPTIONAL - Nice to have

### 14. Canonical-Tag fuer SEO

**Status:** 🟢 **OPTIONAL**

Kein `<link rel="canonical">` vorhanden. Fuer bessere SEO empfohlen.

### 15. AI-Agent Meta-Tags

**Status:** 🟢 **OPTIONAL**

Zeilen 10-14: Nicht-standardisierte Meta-Tags (`ai-agent-friendly`, etc.). Schaden nicht, bringen aber auch nichts. Koennen bleiben oder entfernt werden.

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

---

## 📋 Empfohlene Reihenfolge fuer die Umsetzung

### Phase 1: Kritische Fixes (VOR Launch)
1. Formspree einrichten (#1)
2. Unsplash-Fallbacks entfernen (#2)
3. Schema.org-Bild fixen (#3)
4. Video komprimieren (#6)

### Phase 2: Technische Haertung (VOR Launch)
5. Tailwind fuer Produktion kompilieren (#4)
6. Lucide Version fixieren (#5)
7. Google Fonts lokal hosten (#12)
8. Cookie-Banner mit Ablehnen-Option (#11)
9. Datenschutz um Formspree ergaenzen (#13)

### Phase 3: Feinschliff (VOR oder kurz NACH Launch)
10. Title-Tag anpassen (#7)
11. og:image absolute URL (#8)
12. Favicon erstellen (#9)
13. Copyright-Jahr (#10)
14. Canonical-Tag (#14)

### Phase 4: Launch
- Auf Webserver hochladen
- Domain konfigurieren
- SSL-Zertifikat pruefen
- Alle Formulare live testen
- Google Search Console einrichten

---

## 📊 Versions-Historie

| Version | Datum | Aenderungen |
|---------|-------|-------------|
| V.0.1.0 | 05.02.2026 | E407 ergaenzt, Seelachsfilet-Typo, Linsenbratlinge-Allergene gefixt |
| V.0.0.7 | 11.01.2026 | Allergen-Korrekturen laut Original-Speisekarte |
| V.0.0.6 | 11.01.2026 | Reservierungshinweis + Weihnachts-Easteregg deaktiviert |
| V.0.0.5 | 10.01.2026 | Social Media, Email, Oeffnungszeiten finalisiert |
| V.0.0.4 | - | Rechtliche Texte wiederhergestellt |
| V.0.0.3 | - | Basis-Website |

---

**Zuletzt aktualisiert:** 05.02.2026
