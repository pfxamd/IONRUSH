# IONRUSH — Morocco 2032

A complete, original **fictional** electric racing championship website set entirely in Morocco. Built using 40 commissioned concept visuals, structured championship data, and accessible, responsive, static pages.

## What's included

- 50 static HTML pages, including 9 key destinations and individual team, driver, circuit and race detail pages.
- 40 locally stored, named WebP assets mapped to specific content.
- Eight fictional teams, sixteen fictional drivers and eight Moroccan-inspired circuits.
- Eight complete race result tables with one internally consistent 2032 points championship.
- Interactive fictional race-replay diagrams (synthetic illustrative motion, not telemetry).
- Functional mobile navigation, driver/team standings tabs, and technology hotspot viewer.
- Responsive desktop and mobile layouts, lazy loading and reduced-motion support.
- Standalone prebuilt `dist/` directory that requires no runtime packages or application server.

## Preview locally

```sh
python3 -m http.server 8000 --directory dist
```

Open `http://localhost:8000/`.

## Rebuild

```sh
python3 src/build.py
```

The generator uses Python's standard library only and rebuilds the `dist/` directory from `src/data.py` and the checked-in `public/assets/` content.

## Static hosting

The complete deployable website is in `dist/`. Deploy the **contents** of that folder at the hosting root. Links are relative and also work under a GitHub Pages project subpath (`/IONRUSH/`).

Deployment is **not** configured: no Pages workflow, hosting settings or automatic publishing instructions are activated in this source package.

## Scope / limitations

- All circuits, teams, people, events, venues, results and technical specifications are **fictional**.
- Concept replay animation visualizes synthetic positions; it does not display real timing information.
- The engineering cutaway is conceptual art, not a certified mechanical drawing.
- The landing hero uses layered photographic motion. It is **not** a 3D vehicle model.
- Web fonts are optional remote resources; system font fallbacks preserve legibility offline.

## Asset organization

Photos are numbered `01`–`40` using descriptive filenames under `public/assets/img/`. The generated website carries the same files under `dist/assets/img/`. Asset mappings are defined in `src/data.py`.

## Publish on GitHub Pages (without a custom build workflow)

The deployment helpers upload the full source to `main`, place the prebuilt site under `docs/`, and configure Pages to serve `main` + `/docs`. They never force-push and do not add a custom GitHub Actions workflow. GitHub authentication is required on the machine running the helper.

Linux / macOS (Git and GitHub CLI required):

```sh
bash publish-pages.sh
```

Windows PowerShell (Git and GitHub CLI required):

```powershell
powershell -ExecutionPolicy Bypass -File .\publish-pages.ps1
```

If needed, authenticate first with `gh auth login`. After completion, check `https://pfxamd.github.io/IONRUSH/`. The first GitHub Pages build can take a few minutes.

On Windows, double-click `publish-pages.bat` instead of typing the PowerShell command, if Git and GitHub CLI are already installed and authenticated.
