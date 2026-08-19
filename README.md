# Hochzeitsfotografie – Portfolio & Landingpage

Eine schlanke, elegante One-Page-Website für Hochzeitsfotografie. Kein Build-Prozess, keine Abhängigkeiten – nur `index.html`, direkt bereit für GitHub Pages.

## Vor dem Online-Gehen: Platzhalter ersetzen

Im Editor nach `[` suchen, um alle Stellen zu finden:

| Platzhalter | Ersetzen durch |
|---|---|
| `[DEIN NAME]` | Dein Name / Studioname |
| `[deine@email.de]` | Deine Kontakt-E-Mail (kommt an 3 Stellen vor) |
| `[Telefonnummer]` | Deine Telefonnummer |
| `[instagram-handle]` | Dein Instagram-Nutzername (ohne @) |
| `[Stadt / Region]` | Dein Standort / Einzugsgebiet |

### Eigene Fotos einfügen

Aktuell zeigt die Seite Platzhalter-Kacheln (`<div class="ph-img">…</div>`) für das Porträtfoto und die 9 Galeriebilder. Jede davon ersetzt du durch ein echtes Bild:

```html
<!-- vorher -->
<div class="ph-img"><div class="ph-icon">…</div></div>

<!-- nachher -->
<img src="bilder/hochzeit-01.jpg" alt="Brautpaar am See bei Sonnenuntergang" class="ph-img">
```

Am besten legst du einen Ordner `bilder/` an, komprimierst die Fotos vorher (z.B. mit [Squoosh](https://squoosh.app) auf WebP/JPEG, ca. 1600px breite Kante reicht für Web) und verlinkst sie relativ.

### Impressum & Datenschutz

Als Fotograf:in mit Kontaktformular bist du in Deutschland zu einem **Impressum** und einer **Datenschutzerklärung** verpflichtet. Die Footer-Links dafür sind als Platzhalter (`href="#"`) angelegt – bitte durch echte Unterseiten ersetzen (z.B. mit einem [Impressum-Generator](https://www.e-recht24.de/impressum-generator.html)).

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
