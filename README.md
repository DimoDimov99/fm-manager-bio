# Virtual Football Manager Site

Plain HTML + CSS. No build step, no dependencies. Open `index.html` in a browser.

## Structure
- `index.html` – bio, photo, list of seasons
- `seasons/season-N.html` – one page per season
- `css/styles.css` – shared styling; global colors and fonts are variables at the top
- `css/seasons.css` – per-season club colors and background photos
- `css/manager.css` – size, crop, shape and effects of the manager photo
- `images/` – photos (replace the SVG placeholders; JPG/WebP also fine)

## Add a new season
1. Copy `seasons/season-2.html` to `seasons/season-3.html`.
2. Edit the title, club, text, photo and statistics.
3. Set `<body class="season-page season-3">` and add a `.season-3` block in `css/seasons.css`.
4. Add a link in the nav of every page and a card in `index.html`.
5. In season 2, replace "Next season coming soon" with a link to season 3.

## Season colors and background (one file)
Everything season-specific lives in `css/seasons.css`: one block per season (`.season-1`, `.season-2`, ...).

- Club colors: `--club-primary`, `--club-secondary`, `--club-on-primary` (text color on the top bar; use a dark color if the primary is light).
- Background photo: `--season-bg: url('../images/your-photo.jpg')` and `--season-bg-opacity` (0 to 1).
- Optional: `--season-bg-size` (`cover`, `contain`, `60%`), `--season-bg-position` (`center`, `top`, `20% 50%`), `--season-bg-repeat`, `--season-bg-filter` (`grayscale(1)`, `blur(4px)`).
- Default values for all seasons are in `:root` in `css/styles.css`; anything not set in a season block falls back to them.
- Stat cards have a colored edge by topic: add `stat--good`, `stat--bad`, `stat--gold`, or leave the blue default.

New season checklist: copy the page, set `<body class="season-page season-3">`, add a `.season-3` block in `css/seasons.css`.

## Manager photo
Edit the variables at the top of `css/manager.css`:
- Size: `--manager-img-width`; shape of the frame: `--manager-img-aspect` (`4 / 5`, `1 / 1`, `3 / 2`).
- Crop: `--manager-img-fit` (`cover` or `contain`) and `--manager-img-position` (`center 20%` keeps faces in frame).
- Look: `--manager-img-radius` (`50%` with `1 / 1` gives a circle), `--manager-img-border`, `--manager-img-shadow`, `--manager-img-filter`, `--manager-img-opacity`.

