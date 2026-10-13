# Expenses website

The public pages of the Expenses Android app (GitHub Pages): home, privacy policy, terms, and `config.json`, the
app's remote settings. The app reads `config.json` at most every 6 hours. Nothing is sent to it.

## config.json

| Field | What it does |
| --- | --- |
| `minVersionCode` | Builds below this number show "Update needed" until updated. `0` = off. The build number is in More (the number in brackets). |
| `notice` | A card on More: `{ "id": "launch-1", "title": "…", "body": "…", "url": "https://…" }`. A new `id` shows it again to everyone. `null` = none. |
| `off` | Pause features that turned out broken: any of `"import"`, `"notifications"`, `"export"`, `"private"`, `"sms"`. |
| `freePremium` | `true` gives everyone Premium (a launch offer, or an apology). |
| `contact` | Support e-mail for More → Contact. `null` = this site's contact section. |

A wrong file is ignored by the app (it keeps the last good copy), but check the JSON before pushing
(`python3 -m json.tool config.json`). Changes reach phones within about 6 hours.
