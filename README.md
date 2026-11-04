# LOGI brand: ECO Admin source

Working copies of the LOGI brand's files in WBR's in-house CMS (ECO Admin). The files keep their CMS names, the live Bootstrap 4 markup and the CMS class names (`.header-bottom`, `#header_bottom`, `#sb-page-content`), so changes made here can be pasted straight back into ECO Admin.

This isn't a standalone site. For the Bootstrap 5 portfolio version of LogiPharma EU, see [wbr-logipharma-eu-rebrand-2026](https://github.com/leo12534/wbr-logipharma-eu-rebrand-2026).

## How the brand is built

1. **The rebrand site builds the brand.** [logirebrand.wbresearch.com](https://logirebrand.wbresearch.com/) (event `1006033`) is where every change to `logi.css` and every new site-wide HTML block is made and tested.
   LogiPharma EU was the first event rebranded, so the rebrand site still uses its colours, logos and matrix texture. That's why `1006033.css` looks like `1006035.css`.
2. **Each event only sets its values.** A LOGI event such as LogiPharma EU loads the same `logi.css` and blocks. Its numbered sheet (`1006035.css`) sets that event's colours, logos, matrix texture and nav CTA colours as `:root` variables.

## Files

```
wbr-logi-eco/
├── rebrand/                   logirebrand.wbresearch.com, event 1006033
│   ├── logi.css               brand sheet, loaded by every LOGI event
│   ├── 1006033.css            the rebrand site's event sheet; starting point for a new event
│   └── homepage.html          site-wide HTML blocks, as built on the rebrand site
├── events/
│   └── 1006035-logipharma-eu/
│       ├── 1006035.css        LogiPharma EU's values
│       └── homepage.html      LogiPharma EU's homepage, kept in case it has blocks the rebrand site doesn't
└── shell/
    └── style.css              the CMS's shared shell; reference only
```

| File | CMS location |
| --- | --- |
| `rebrand/logi.css` | `/UploadedFiles/EventPage/brands/logi/logi.css` |
| `rebrand/1006033.css` | `/UploadedFiles/EventPage/1006033/1006033.css` |
| `rebrand/homepage.html`, `events/<id>-<event>/homepage.html` | Homepage content inside `#sb-page-content` |
| `events/<id>-<event>/<id>.css` | `/UploadedFiles/EventPage/<id>/<id>.css` |
| `shell/style.css` | `/WBR/CSS/events/style.css` |

An event's `homepage.html` is kept in case that event has a block the rebrand site doesn't have yet. Once that block is added to the rebrand site, it belongs in `rebrand/homepage.html`.

Each `homepage.html` was captured from the rendered page, so it includes markup the CMS adds when it renders modules, such as speaker listings and sponsor logos.

## Adding a LOGI event

Copy `rebrand/1006033.css` to `events/<id>-<event>/<id>.css`, e.g. `events/1006036-logipharma-us/1006036.css`, then change the colours, logos and other values for that event.

## Updating the CMS

ECO Admin loads each sheet with a version query (`logi.css?v=12`, `1006035.css?v=7`). After uploading a changed file, bump its version in the CMS so browsers pick up the new copy.
