# LOGI brand: ECO Admin source

Working copies of the LOGI brand's files in WBR's in-house CMS (ECO Admin). The files keep their CMS names, the live Bootstrap 4 markup and the CMS class names (`.header-bottom`, `#header_bottom`, `#sb-page-content`), so changes made here can be pasted straight back into ECO Admin.

This isn't a standalone site. For the Bootstrap 5 portfolio version of LogiPharma EU, see [wbr-logipharma-eu-rebrand-2026](https://github.com/leo12534/wbr-logipharma-eu-rebrand-2026).

## Files

| File | CMS location | Shared by |
| --- | --- | --- |
| `shell/style.css` | `/WBR/CSS/events/style.css` | Every ECO event. Reference only: it isn't edited in ECO Admin. |
| `brands/logi/logi.css` | `/UploadedFiles/EventPage/brands/logi/logi.css` | Every LOGI event |
| `events/1006035-logipharma-eu/1006035.css` | `/UploadedFiles/EventPage/1006035/1006035.css` | LogiPharma EU only |
| `events/1006035-logipharma-eu/homepage.html` | Homepage content inside `#sb-page-content` | LogiPharma EU only |

`homepage.html` was captured from the rendered live page, so it includes markup the CMS adds when it renders modules, such as speaker listings and sponsor logos.

## Adding a LOGI event

Add a folder under `events/` named `<event id>-<event>`, e.g. `events/1006036-logipharma-us/`, with that event's `<id>.css`.

## Updating the CMS

ECO Admin loads each sheet with a version query (`logi.css?v=12`, `1006035.css?v=7`). After uploading a changed file, bump its version in the CMS so browsers pick up the new copy.
