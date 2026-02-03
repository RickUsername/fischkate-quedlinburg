# Fischkate Website - Offene Punkte & TODOs

> **Letztes Update:** 11.01.2026 (Version V.0.0.7)

---

## 🔴 KRITISCH - Muss behoben werden

### 1. Formspree Formulare (2x PLACEHOLDER)

**Status:** ⚠️ **OFFEN**

**Zeilen:** ~1300, ~1425

**Problem:** Beide Kontaktformulare nutzen Formspree.io mit PLACEHOLDER als Endpunkt

**Betrifft:**
- Blitzbewerbung (Jobs-Sektion): `action="https://formspree.io/f/PLACEHOLDER"`
- Tischreservierung (Kontakt-Sektion): `action="https://formspree.io/f/PLACEHOLDER"`

**Lösung erforderlich:**
1. Formspree-Account erstellen auf https://formspree.io
2. Zwei Formulare erstellen:
   - "Fischkate Bewerbungen"
   - "Fischkate Tischreservierungen"
3. Die generierten Form-IDs (z.B. `xyzabc123`) in `index.html` eintragen
4. Formulare testen

**Priorität:** 🔥 **VOR LAUNCH KRITISCH**

---

## ✅ ERLEDIGT

### 2. Email-Adresse ✅ 
**Status:** ✅ **ERLEDIGT**

Email-Adresse `Fisch-Kate-qlb@gmx.de` wurde in Datenschutz und Impressum eingetragen.

### 3. Umsatzsteuer-ID ✅ 
**Status:** ✅ **ERLEDIGT**

Sektion wurde entfernt - Restaurant hat keine Umsatzsteuer-ID (rechtlich nicht erforderlich).

### 4. Social Media Links ✅ 
**Status:** ✅ **ERLEDIGT**

Links wurden eingetragen:
- Facebook: https://www.facebook.com/janabachmannfischkate
- Instagram: https://www.instagram.com/jana.bachmann/

### 5. Öffnungszeiten ✅ 
**Status:** ✅ **ERLEDIGT**

- Di-Sa: 10:00 - 21:00 Uhr
- Sonntag & Montag: Ruhetag

### 6. Cookie Banner Persistenz ✅ 
**Status:** ✅ **ERLEDIGT**

Cookie-Banner mit LocalStorage-Persistenz ist implementiert:
- Banner wird beim ersten Besuch angezeigt
- "Alles klar" Button speichert Zustimmung
- Persistenz über Seitenbesuche funktioniert

### 7. Navigation zu Allergenen ✅ 
**Status:** ✅ **ERLEDIGT**

Link im Footer führt korrekt zur Allergene & Zusatzstoffe Sektion.

### 8. Weihnachts-Easteregg Deaktivierung ✅ 
**Status:** ✅ **ERLEDIGT** (V.0.0.6)

Weihnachtsmütze, Schnee-Animation und "Oberwichtel"-Textwechsel wurden auskommentiert für Reaktivierung zur nächsten Weihnachtszeit.

### 9. Reservierungsbestätigungs-Hinweis ✅ 
**Status:** ✅ **ERLEDIGT** (V.0.0.6)

Informativer Hinweis wurde zum Reservierungsformular hinzugefügt: "Ihre Reservierung wird erst nach unserer Bestätigung gültig."

---

## 🟡 WICHTIG - Sollte ergänzt werden

### 10. KI-Agenten-Optimierung 🤖

**Status:** 🟡 **GEPLANT**

**Ziel:** Website für KI-Agenten lesbar und interaktiv machen

**Use Cases:**
- KI-Agenten können automatisch Tische reservieren
- KI-Agenten können Bewerbungen einreichen
- KI-Agenten können die Speisekarte auslesen und analysieren
- Persönliche KI-Assistenten können Gäste bei der Bestellung beraten

**Zu implementieren:**
- [ ] **Structured Data erweitern**
  - Schema.org Menu markup für Speisekarte
  - JSON-LD für alle Gerichte mit Preisen, Allergenen, Zutaten
  - OpeningHours schema bereits vorhanden ✅
  
- [ ] **API-ähnliche Zugänglichkeit**
  - Semantic HTML mit klaren `data-*` Attributen
  - ARIA-Labels für bessere Maschinenlesbarkeit
  - Formulare mit eindeutigen IDs und Labels
  
- [ ] **robots.txt & AI-freundliche Meta-Tags**
  - AI-Agent friendly meta tags
  - Klare Seitenstruktur mit heading hierarchy
  
- [ ] **Optionale JSON API**
  - Endpoint für Speisekarte als JSON
  - Endpoint für verfügbare Zeiten (Reservierung)
  - Job-Angebote als strukturierte Daten

**Technische Umsetzung:**
```html
<!-- Beispiel: Speisekarte für KI lesbar -->
<article itemscope itemtype="https://schema.org/MenuItem" data-dish-id="vorspeise-1">
  <h4 itemprop="name">Fischsuppe „A la Bouillabaisse"</h4>
  <meta itemprop="price" content="9.90">
  <meta itemprop="priceCurrency" content="EUR">
  <p itemprop="description">Provenzalische Delikatesse (mit Wermut), dazu Baguette</p>
  <meta itemprop="allergens" content="h,m,k,f,b,g,4,e1,i">
</article>
```

**Vorteile:**
- Bessere Auffindbarkeit in KI-Suchmaschinen
- Kunden können ihren persönlichen KI-Assistenten nutzen
- Automatisierte Reservierungen und Bewerbungen
- SEO-Optimierung als Nebeneffekt

**Priorität:** 🟡 Wichtig für Zukunftssicherheit

---

### 11. Google Bewertungen Integration

**Status:** 🟡 **OPTIONAL VERBESSERUNG**

**Aktuell:**
```html
<blockquote>
    "Das Essen war so frisch zubereitet..."
    <footer>- Auszug Google Bewertung</footer>
</blockquote>
```

**Mögliche Verbesserungen:**
- [ ] Google Review Widget einbinden
- [ ] Mehr Bewertungen anzeigen (Carousel)
- [ ] Link zu Google Business Profil hinzufügen
- [ ] Bewertungs-Sterne animiert darstellen
- [ ] Google Review API nutzen für aktuelle Bewertungen

**Priorität:** 🟡 Nach Launch

---

## 🟢 OPTIONAL - Nice to have

### 12. PDF-Speisekarte Integration

**Status:** 🟢 **IDEE**

**Vorschlag:**
- [ ] Download-Link zur PDF-Speisekarte hinzufügen
- [ ] System zum automatischen Parsen der PDF vorbereiten
- [ ] Oder: Online-Speisekarte als Lead, PDF als Backup

**Datei vorhanden:** `SPEISENKARTE.10.01.2026.pdf`

**Priorität:** 🟢 Nice to have

### 13. Bilder - Fallback URLs überprüfen

**Status:** 🟢 **ÜBERPRÜFEN**

**Problem:** Mehrere Bilder haben Unsplash-Fallback-URLs per `onerror`

**Zu prüfen:**
- [ ] Sind alle lokalen Bilder vorhanden?
- [ ] Funktionieren alle Bildpfade?
- [ ] Fallbacks testen (Bild temporär umbenennen)

**Betroffene Bereiche:**
- Video-Fallback im Hero-Banner
- Team-Bilder
- Galerie-Bilder

**Priorität:** 🟢 Nach Launch

### 14. Analytics & Tracking

**Status:** 🟢 **NOCH NICHT IMPLEMENTIERT**

**Vorschlag:**
- [ ] Google Analytics einbinden (DSGVO-konform)
- [ ] Cookie-Banner um Analytics erweitern
- [ ] Tracking von Reservierungsanfragen
- [ ] Conversion-Tracking für Bewerbungen

**Priorität:** 🟢 Optional, nach Launch

---

## ✅ BEREITS VOLLSTÄNDIG IMPLEMENTIERT

Die folgenden Features sind komplett fertig:

- ✅ Vollständige Speisekarte mit allen Kategorien (Vorspeisen, Hauptgerichte, Fischbaguettes, etc.)
- ✅ Vollständige Getränkekarte (Biere, Weine, Rosé, etc.)
- ✅ Allergene & Zusatzstoffe Listen
- ✅ Datenschutzerklärung (vollständig, rechtlich korrekt)
- ✅ Impressum (vollständig, rechtlich korrekt)
- ✅ Job-Anzeigen (4 Stellen: Service, Koch, Thekenkraft, Spülkraft)
- ✅ Blitzbewerbung-System
- ✅ Reservierungsformular mit Bestätigungshinweis
- ✅ Responsive Design (Mobile, Tablet, Desktop)
- ✅ Mobile Navigation
- ✅ Mediathek mit Bildern
- ✅ Videos eingebunden
- ✅ SEO-optimiert (Meta-Tags, Structured Data)

---

## 📋 Prioritäten-Übersicht

### 🔥 Vor Website-Launch (KRITISCH)
1. **Formspree Setup** - MUST HAVE
   - Account erstellen
   - 2 Formulare anlegen
   - IDs eintragen und testen

### 🟡 Nach Launch (Bei Gelegenheit)
2. **KI-Agenten-Optimierung** - Zukunftssicherheit
3. **Google Bewertungen** verbessern
4. **Bilder-Fallbacks** überprüfen
5. **PDF-Speisekarte** System überlegen

### 🟢 Langfristig (Optional)
6. **Analytics** einrichten
7. **SEO** weiter optimieren
8. **Performance** messen und verbessern

---

## 🔧 Nächste Schritte

### Schritt 1: Formspree Setup ⚡ JETZT
1. Auf https://formspree.io registrieren
2. Zwei Formulare anlegen:
   - Formular 1: "Fischkate Bewerbungen"
   - Formular 2: "Fischkate Tischreservierungen"
3. Form-IDs kopieren (Format: `xyzabc123`)
4. In `index.html` nach `formspree.io/f/PLACEHOLDER` suchen
5. PLACEHOLDER durch echte IDs ersetzen
6. Website lokal öffnen und beide Formulare testen

### Schritt 2: Final-Test 🧪
- [ ] Alle Links testen (Navigation, Social Media, externe Links)
- [ ] Beide Formulare testen (Bewerbung & Reservierung)
- [ ] Mobile Ansicht auf echtem Gerät prüfen
- [ ] Ladezeiten messen
- [ ] Browser-Kompatibilität testen

### Schritt 3: Launch 🚀
- [ ] Auf Webserver hochladen
- [ ] Domain konfigurieren
- [ ] SSL-Zertifikat prüfen
- [ ] Google Search Console einrichten
- [ ] Backups einrichten

---

## 📊 Versions-Status

| Version | Datum | Status | Änderungen |
|---------|-------|--------|------------|
| V.0.0.7 | 11.01.2026 | ✅ Aktuell | Fischguide JavaScript-Fehler behoben |
| V.0.0.6 | 11.01.2026 | ✅ | Reservierungshinweis + Weihnachts-Easteregg deaktiviert |
| V.0.0.5 | 10.01.2026 | ✅ | Social Media, Email, Öffnungszeiten finalisiert |
| V.0.0.4 | - | ✅ | Rechtliche Texte wiederhergestellt |
| V.0.0.3 | - | ✅ | Basis-Website |

---

## 📞 Support & Kontakt

Bei Fragen zur Website:
- **Inhaberin:** Jana Bachmann
- **Email:** Fisch-Kate-qlb@gmx.de
- **Telefon:** 03946 5198488

---

**Zuletzt aktualisiert:** 11.01.2026, 19:58 Uhr
