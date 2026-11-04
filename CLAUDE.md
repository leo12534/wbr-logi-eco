# wbr-logi-eco

Working copies of the LOGI brand's ECO Admin (CMS) files: the brand sheet, each LOGI event's stylesheet and homepage content. This repo mirrors what's live in the CMS. It isn't a standalone site.

**Repository:** https://github.com/leo12534/wbr-logi-eco

## Conventions

- Match the live CMS: Bootstrap 4 classes (`ml-*`, `font-weight-*`, `data-toggle`) and CMS selectors (`.header-bottom`, `#header_bottom`, `#sb-page-content`, `.navbar-nav>li:last-child`). Don't convert anything to Bootstrap 5 or the ECO2 template's `#eco-*` selectors. That conversion lives in `event-sites/wbr-logipharma-eu-rebrand-2026`.
- `shell/style.css` is the CMS's shared shell, kept for reference. Don't edit it. Override it from `brands/logi/logi.css`.
- `brands/logi/logi.css` holds brand rules shared by every LOGI event. Per-event values go in that event's `<id>.css` as `:root` variables, read by `logi.css` with fallbacks (e.g. `var(--nav-last-btn-bg, var(--event-color-accent))`).
- Per-event sheets keep the CMS's commented `:root` sections (`/* Event Colors */`, `/* Logos */`, ...).
- HTML is body content only, ready to paste into the CMS.
- The CMS uses `!important` heavily to beat its own shell. Keep existing ones. Add new ones only where a test shows they're needed.
- Live sites return 403 to headless clients. Fetch them with a normal Chrome user agent.
