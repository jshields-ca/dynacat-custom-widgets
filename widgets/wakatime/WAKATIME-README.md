# WakaTime Widget

> Part of [dynacat-custom-widgets](../../README.md) — a collection of custom widgets for [Dynacat](https://github.com/Panonim/dynacat).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](../../LICENSE)
[![WakaTime API](https://img.shields.io/badge/WakaTime-API-informational)](https://wakatime.com/developers)

A [Dynacat](https://github.com/Panonim/dynacat)  widget that pulls from the [WakaTime API](https://wakatime.com/developers) and displays your coding metrics — total time, daily average, best day, top languages, and top projects — directly on your dashboard.

## Widget

Displays total coding time, daily average, best day, and a ranked breakdown of your top languages and projects for the past 7 days. Refreshes every 30 minutes.

## Prerequisites

- A running [Dynacat](https://github.com/Panonim/dynacat) instance
- A [WakaTime](https://wakatime.com) account with an editor plugin installed
- Your WakaTime Secret API Key — [wakatime.com/settings/api-key](https://wakatime.com/settings/api-key)

## Setup

### 1. Set your API key

Add `WAKATIME_API_KEY` to the environment where Dynacat/Glance runs.

**.env file** (local installs):
```
WAKATIME_API_KEY=waka_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

**Docker Compose:**
```yaml
environment:
  - WAKATIME_API_KEY=waka_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

**Shell:**
```sh
export WAKATIME_API_KEY=waka_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 2. Add the widget to your `dynacat.yml`

Copy the widget block from [`wakatime-widget.yml`](./wakatime-widget.yml) and paste into a `widgets:` list in your config:

```yaml
pages:
  - title: Home
    columns:
      - size: small
        widgets:
          - type: custom-api
            title: WakaTime
            # ... (see wakatime-widget.yml for the full block)
```

### 3. Restart Dynacat

```sh
# systemd
sudo systemctl restart dynacat

# Docker
docker compose restart dynacat
```

## Configuration

| Variable | Required | Description |
|---|---|---|
| `WAKATIME_API_KEY` | Yes | Your WakaTime Secret API Key |

### Time range

The weekly overview defaults to `last_7_days`. To change it, swap the URL suffix in your config:

| Suffix | Period |
|---|---|
| `stats/last_7_days` | Past 7 days *(default)* |
| `stats/last_30_days` | Past 30 days |
| `stats/last_6_months` | Past 6 months |
| `stats/last_year` | Past year |
| `stats/all_time` | All time |

## How it works

The widget uses the built-in `custom-api` widget type — no extra binary or server needed. The YAML is pasted directly into `glance.yml`.

- Fetches from the [WakaTime API](https://wakatime.com/developers) using your API key as a query parameter
- Adapts automatically to your Dynacat/Glance theme (no hardcoded colors)
- Hover any language or project row to see the exact time tracked
- Long names are truncated cleanly to fit any column width

---

Built with [Claude Code](https://claude.ai/code) · Created by [jshields-ca](https://github.com/jshields-ca) · [scootr.ca](https://scootr.ca)

## License

MIT — see [LICENSE](../../LICENSE)
