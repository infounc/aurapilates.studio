# aurapilates.studio

Platzhalter-Website für Aura Reformer Pilates: Startseite mit Logo und „Coming soon“
plus Impressum (`/impressum/`) und Datenschutz (`/datenschutz/`). Ausgeliefert über GitHub Pages.

## Datenschutz / Impressum ändern

`datenschutz.md` bzw. `impressum.md` bearbeiten (geht auch direkt auf github.com über das Stift-Symbol) und
den Text ändern. Zeilenumbrüche bleiben erhalten, Leerzeile = neuer Absatz,
`## ` = Abschnittsüberschrift, `### ` = Unterabschnitt.
Nach dem Commit ist die Änderung nach ca. 1 Minute online.

## Dateien

| Datei | Inhalt |
|---|---|
| `index.html` | Startseite (Logo + Coming soon) |
| `datenschutz.md` | Datenschutztext → `/datenschutz/` |
| `impressum.md` | Impressum → `/impressum/` |
| `_layouts/default.html` | Rahmen für Textseiten (Logo oben, Links im Footer) |
| `assets/` | Logo, Favicon, `style.css` |
| `CNAME` | Custom Domain für GitHub Pages |

## Hosting

- GitHub → Settings → Pages: *Deploy from a branch*, `main`, `/ (root)`.
- DNS (Namecheap) für `aurapilates.studio`:
  - `A` @ → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
  - `AAAA` @ → `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
  - `CNAME` www → `infounc.github.io.`
- Danach in Settings → Pages „Enforce HTTPS“ aktivieren.

## Lokal ansehen

```bash
docker run --rm -v "$PWD":/site -w /site -p 4000:4000 ruby:3.3 \
  sh -c 'gem install jekyll -v "~> 3.10" kramdown-parser-gfm webrick && jekyll serve -H 0.0.0.0'
```
