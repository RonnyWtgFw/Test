# Hochzeitsfotografie – Portfolio & Landingpage

Eine schlanke, elegante One-Page-Website für Hochzeitsfotografie. Kein Build-Prozess, keine Abhängigkeiten – nur `index.html`, direkt bereit für GitHub Pages.

## Kontaktdaten

Name, E-Mail, Telefon, Instagram-Link und Standort (Ludwigsburg / Baden-Württemberg) sind bereits eingetragen. Vor dem Online-Gehen bleibt nur noch:

### Eigene Fotos einfügen

Alle 9 Galerie-Kacheln zeigen bereits echte Fotos aus `bilder/` (komprimiert auf max. 1800px Kantenlänge, EXIF-Metadaten entfernt). Der „Über mich“-Bereich kommt aktuell bewusst ohne Porträtfoto aus – möchtest du später eins ergänzen, fügst du im `about-text`-Block in `index.html` ein Bild hinzu, z.B.:

```html
<img src="bilder/portrait.jpg" alt="Ronny Martens" class="ph-img tall" style="max-width:280px; margin-bottom:24px;">
```

Weitere Galeriefotos ergänzt du genauso – neue Fotos vorher komprimieren (z.B. mit [Squoosh](https://squoosh.app) auf WebP/JPEG, ca. 1600–1800px lange Kante reicht für Web) und in `bilder/` ablegen.

### Impressum & Datenschutz

`impressum.html` und `datenschutz.html` sind angelegt, im Footer von `index.html` verlinkt und mit deiner Anschrift (New-York-Ring 45, 71686 Remseck am Neckar) befüllt. Die Umsatzsteuer-ID in `impressum.html` nur eintragen, falls vorhanden, sonst den Abschnitt entfernen.

Die Datenschutzerklärung deckt den aktuellen Stand der Seite ab (Hosting via GitHub Pages, Google Fonts, mailto-Kontaktformular, Instagram-Link, keine Cookies/Tracking). Baust du später weitere Dienste ein (z.B. ein echtes Server-Kontaktformular, Web-Analyse), muss `datenschutz.html` entsprechend ergänzt werden.

Diese Texte sind eine solide Grundlage, aber keine Rechtsberatung – bei Unsicherheiten lohnt sich eine kurze Prüfung durch einen Anwalt oder einen Generator wie [e-recht24.de](https://www.e-recht24.de/impressum-generator.html).

### Kontaktformular

Das Formular nutzt aktuell `mailto:` – es öffnet beim Absenden das E-Mail-Programm des Besuchers mit vorausgefüllter Nachricht. Das funktioniert ohne Server, ist aber auf Mobilgeräten manchmal unzuverlässig. Für ein echtes, serverloses Formular (Zustellung direkt per E-Mail, ohne dass der Nutzer sein Mailprogramm öffnet) empfiehlt sich z.B. [Formspree](https://formspree.io) (kostenloser Tarif reicht meist aus) – dafür einfach `action` im `<form>`-Tag auf die Formspree-URL ändern und `method="post" enctype="text/plain"` entfernen.

## Lokal ansehen

Einfach `index.html` im Browser öffnen, oder mit einem lokalen Server:

```bash
python3 -m http.server 8000
# dann im Browser: http://localhost:8000
```

## Online stellen mit GitHub Pages (kostenlos)

1. Änderungen committen und in den Standard-Branch (`main`) pushen bzw. mergen.
2. Im Repository auf GitHub: **Settings → Pages**.
3. Unter **Build and deployment** → **Source**: `Deploy from a branch` wählen.
4. Branch `main`, Ordner `/ (root)` auswählen, **Save**.
5. Nach ein bis zwei Minuten ist die Seite unter `https://<dein-github-name>.github.io/<repo-name>/` erreichbar.

Eigene Domain (optional): Unter **Settings → Pages → Custom domain** deine Domain eintragen und beim Domain-Anbieter einen `CNAME`-Eintrag auf `<dein-github-name>.github.io` anlegen.

## Struktur

- `index.html` – komplette Seite (HTML, CSS, JS in einer Datei)
- Schriften: [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) (Überschriften) & [Inter](https://fonts.google.com/specimen/Inter) (Fließtext), via Google Fonts eingebunden
