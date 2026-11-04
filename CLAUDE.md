# wbr-logi-eco

Working copies of the LOGI brand's ECO Admin (CMS) files. This repo mirrors what's live in the CMS. It isn't a standalone site.

**Repository:** https://github.com/leo12534/wbr-logi-eco

## Where changes go

- `rebrand/` mirrors the rebrand site, logirebrand.wbresearch.com (event `1006033`). Brand changes happen here: `rebrand/logi.css` and new site-wide HTML blocks in `rebrand/homepage.html`.
- `events/<id>-<event>/<id>.css` holds one event's values only: colours, logos, matrix texture, nav CTA colours, as `:root` variables. Don't put layout rules or new blocks in an event sheet. If an event needs something new, add it to `logi.css` behind a variable with a fallback (e.g. `var(--nav-last-btn-bg, var(--event-color-accent))`), then set the variable in the event sheet.
- A new LOGI event starts as a copy of `rebrand/1006033.css`.
- `shell/style.css` is the CMS's shared shell, kept for reference. Don't edit it. Override it from `rebrand/logi.css`.

## Conventions

- Match the live CMS: Bootstrap 4 classes (`ml-*`, `font-weight-*`, `data-toggle`) and CMS selectors (`.header-bottom`, `#header_bottom`, `#sb-page-content`, `.navbar-nav>li:last-child`). Don't convert anything to Bootstrap 5 or the ECO2 template's `#eco-*` selectors. That conversion lives in `event-sites/wbr-logipharma-eu-rebrand-2026`.
- Event sheets keep the CMS's commented `:root` sections (`/* Event Colors */`, `/* Logos */`, ...).
- HTML is body content only, ready to paste into the CMS.
- The CMS uses `!important` heavily to beat its own shell. Keep existing ones. Add new ones only where a test shows they're needed.
- Live sites return 403 to headless clients. Fetch them with a normal Chrome user agent.
