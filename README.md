# dynacat-custom-widgets

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Dynacat](https://img.shields.io/badge/Dynacat-compatible-4CAF50)](https://github.com/Panonim/dynacat)
[![Glance](https://img.shields.io/badge/Glance-compatible-blue)](https://github.com/glanceapp/glance)
[![custom-api](https://img.shields.io/badge/type-custom--api-informational)](https://github.com/Panonim/dynacat)

A collection of drop-in `custom-api` widgets for [Dynacat](https://github.com/Panonim/dynacat) (and [Glance](https://github.com/glanceapp/glance)). Paste a YAML block into your config and go — no extra server required.

See also the official community widget registry: [dynawidgets](https://github.com/Panonim/dynawidgets)

---

## Widgets

| Widget | Description | Config |
|--------|-------------|--------|
| [Todoist Dashboard](widgets/todoist/TODOIST-README.md) | Karma, daily productivity stats, open task count with P1–P4 breakdown, active projects, and top labels — all in one widget | [todoist-dashboard.yml](widgets/todoist/todoist-dashboard.yml) |
| [WakaTime](widgets/wakatime/WAKATIME-README.md) | Weekly coding time, daily average, best day, top languages & projects | [wakatime-widget.yml](widgets/wakatime/wakatime-widget.yml) |
| [CAD Exchange Rates](widgets/currency-exchange-rate/CURRENCY-EXCHANGE-RATE-README.md) | CAD → USD and EUR exchange rates with last-synced timestamp, updated daily | [currency-exchange-rate.yml](widgets/currency-exchange-rate/currency-exchange-rate.yml) |

---

## Quick Start

1. Open the README for the widget you want (links above).
2. Set the required environment variable(s) in your Dynacat `.env` file.
3. Copy the YAML from the widget's config file and paste it into a `widgets:` list in your `glance.yml` / `config.yml`.
4. Restart Dynacat.

A combined `.env` reference for all widgets is in [`.env.example`](.env.example).

---

## Environment Variables

| Variable | Widget | Description |
|----------|--------|-------------|
| `TODOIST_API_TOKEN` | Todoist Dashboard | Your Todoist personal API token |
| `WAKATIME_API_KEY` | WakaTime | Your WakaTime Secret API Key |
| `HOMEPAGE_VAR_EXCHANGE_KEY` | CAD Exchange Rates | Your ExchangeRate-API v6 key |

---

## Adding a Widget

Each widget lives in its own folder under `widgets/` with a YAML config file and a README. Pull requests welcome.

---

## Credits

Created by [@jshields-ca](https://github.com/jshields-ca) — [scootr.ca](https://scootr.ca)

Built for [Dynacat](https://github.com/Panonim/dynacat). Also compatible with [Glance](https://github.com/glanceapp/glance).

## License

MIT — see [LICENSE](LICENSE)
