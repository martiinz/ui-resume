# Webseitenportfolio (Jekyll)

## Lokal ansehen

```bash
bundle install          # einmalig (und nach Änderungen am Gemfile)
bundle exec jekyll serve --livereload
```

Dann <http://localhost:4000> öffnen. Änderungen erscheinen beim Speichern sofort.
`_config.yml` wird nur beim Start gelesen, nach Änderungen dort den Server neu starten.

## Was wo steht

| Was | Datei |
|---|---|
| Name, Studiengang, E-Mail, LinkedIn, Porträt, PDF-Lebenslauf | `_config.yml` |
| Vorstellungstext auf der Startseite | `index.html` |
| Referenzen (Zitate) | `_data/referenzen.yml` |
| Lebenslauf | `_data/lebenslauf.yml` |
| Nachhaltigkeitskompetenzen (je eine Datei) | `_nachhaltigkeit/*.md` |
| Kernkompetenzen (je eine Datei) | `_kernkompetenzen/*.md` |
| Blogbeiträge / Projekte | `_posts/JJJJ-MM-TT-titel.md` |
| Menü | `_data/navigation.yml` |
| Farben, Schriften, Layout | `assets/css/style.css` (oben die Variablen) |
| Bilder | `assets/img/` |

Bilder für Karten setzt du im Front Matter mit `image: /assets/img/foto.jpg`.
Im Text verwendest du `![Beschreibung]({{ '/assets/img/foto.jpg' | relative_url }})`,
damit der Pfad auch auf GitHub Pages stimmt.

Kompetenzen werden nach `order:` sortiert. Neue Kompetenz = Datei kopieren, Titel und Nummer anpassen.

## Auf GitHub Pages veröffentlichen

1. Neues Repository auf GitHub anlegen und den Ordner pushen (Branch `main`).
2. Im Repo: **Settings → Pages → Source: GitHub Actions**.
3. Jeder Push auf `main` baut und veröffentlicht die Seite automatisch
   (Workflow `.github/workflows/pages.yml`, Fortschritt im Tab **Actions**).

Die Seite erscheint unter `https://<benutzername>.github.io/<repo-name>/`.
Heisst das Repo `<benutzername>.github.io`, liegt sie direkt unter `https://<benutzername>.github.io/`.
