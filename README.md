# GitHub Pages Hub — go34iwb.github.io

Central landing page linking to all project dashboards under `https://go34iwb.github.io/<repo>/`.

## Wie es funktioniert

- Repo-Name **muss** `go34iwb.github.io` heißen → dient die GitHub-User-Pages unter `https://go34iwb.github.io/`.
- `index.html` ruft die GitHub-REST-API auf (`/users/go34iwb/repos?per_page=100`), filtert auf `has_pages: true` und rendert Karten.
- Neue Projekte erscheinen automatisch beim nächsten Laden der Seite.

## Lokales Bearbeiten

```bash
cd /home/hermes/.hermes/projects/20261007_github-pages-hub
# index.html anpassen
git add index.html
git commit -m "Update hub"
git push origin gh-pages
```

Die Live-Seite aktualisiert sich nach ~30–60 Sekunden.

## Diagnose

- `curl -I https://go34iwb.github.io/` → 200 erwartet
- Falls 404: `gh api repos/go34iwb/go34iwb.github.io/pages` → Branch muss `gh-pages` sein
- GitHub-API Rate-Limit: 60 req/h pro IP — Browser-Cache hilft

## Verknüpfte Projekte (Stand heute)

- vw-t6-twin — VW T6 Bus telemetrie → https://go34iwb.github.io/vw-t6-twin/
- bartresen-kueche — Solid-Wood Bartresen-Konstruktion → https://go34iwb.github.io/bartresen-kueche/
- (alle weiteren: automatisch, sobald `has_pages: true`)
