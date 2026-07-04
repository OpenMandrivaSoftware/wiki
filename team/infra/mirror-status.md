---
title: Mirror reliability status
description: Auto-generated mirror reliability ranking (do not edit by hand)
published: true
date: 2026-07-04T07:30:05.000Z
tags: documentation
editor: markdown
dateCreated: 2026-07-04T00:00:00.000Z
---

# Mirror reliability status

> **Auto-generated** page — data as of **2026-07-04 07:30 UTC**, over a rolling **30-day** window. Do not edit by hand: it is regenerated on a schedule. {.is-info}

This ranking is computed automatically — it is not a manual, editorial judgement. Mirrors are ordered by a transparent score:

`score = availability% × content-freshness%`  — a mirror is useful only if it is **both** reachable **and** up to date.

- **Content age** — time since the mirror's own `TIME.txt` (its last sync). This is the **real** content freshness, measured over HTTP; lower is better.
- **Availability** — share of the window the mirror was reachable (Mirrorbits up/down).
- **Scan** — Mirrorbits indexing health (rsync/ftp). *Informational only, not in the score*: a failing scan means Mirrorbits cannot index the mirror (e.g. a changed rsync URL), **not** that its content is stale.
- **Reactivity** — *approximate* proxy (median successful-scan duration), not a measured download speed.
- **Downloads** — client requests / bytes served over the window (popularity, for context).
- **Class** — ⭐⭐⭐ score ≥ 90 · ⭐⭐ ≥ 70 · ⭐ ≥ 40.

| # | Mirror | Country | State | Class | Content age | Avail. | Scan* | Reactivity* | Downloads | Score |
|---|--------|---------|-------|:-----:|------------:|-------:|------:|------------:|----------:|------:|
| 1 | ufpr.br | 🇧🇷 BR | 🟢 up | ⭐⭐⭐ | 14min | 100.0% | 100% | 53s | 73 101 / 100.6 Go | **100** |
| 2 | openmandriva.org | 🇺🇸 US | 🟢 up | ⭐⭐⭐ | 14min | 100.0% | 8% | 149s | 112 874 / 120.4 Go | **100** |
| 3 | ibiblio.org | 🇺🇸 US | 🟢 up | ⭐⭐⭐ | 44min | 100.0% | 0% | — | 227 159 / 204.1 Go | **100** |
| 4 | mirror-services.net | 🇧🇪 BE | 🟢 up | ⭐⭐⭐ | 1h | 100.0% | 100% | 25s | 106 544 / 101.6 Go | **100** |
| 5 | icm.edu.pl | 🇵🇱 PL | 🟢 up | ⭐⭐⭐ | 1h | 100.0% | 100% | 57s | 44 066 / 53.0 Go | **100** |
| 6 | rpmfind.net | 🇫🇷 FR | 🟢 up | ⭐⭐⭐ | 2h | 100.0% | 100% | 29s | 129 787 / 129.9 Go | **100** |
| 7 | tu-chemnitz.de | 🇩🇪 DE | 🟢 up | ⭐⭐⭐ | 3h | 100.0% | 99% | 74s | 50 839 / 62.2 Go | **100** |
| 8 | freedif.org | 🇸🇬 SG | 🟢 up | ⭐⭐⭐ | 3h | 100.0% | 100% | 31s | 66 904 / 87.7 Go | **100** |
| 9 | hostafrica.co.za | 🇿🇦 ZA | 🔴 down | — | 1h | 0.0% | 0% | — | 0 | **0** |
| 10 | garr.it | 🇮🇹 IT | 🔴 down | — | 1h | 0.0% | 0% | — | 0 | **0** |
| 11 | rise.ph | 🇵🇭 PH | 🔴 down | — | 154j | 0.0% | 0% | — | 0 | **0** |
| 12 | mirrorservice.org | 🇬🇧 GB | 🟢 up | — | 154j | 100.0% | 97% | 86s | 13 112 / 16.7 Go | **0** |
| 13 | yandex.ru | 🇷🇺 RU | 🟢 up | — | 154j | 100.0% | 99% | 81s | 11 820 / 14.9 Go | **0** |
| 14 | hs-esslingen.de | 🇩🇪 DE | 🟢 up | — | 154j | 100.0% | 88% | 38s | 12 345 / 15.8 Go | **0** |
| 15 | accum.se | 🇸🇪 SE | 🔴 down | ? | ? | 1.7% | 84% | 333s | 85 147 / 81.9 Go | **0** |
| 16 | northrepo.ca |   | 🔴 down | ? | ? | 0.0% | 0% | — | 0 | **0** |
| 17 | remi.lu | 🇫🇷 FR | 🔴 down | ? | ? | 0.0% | 0% | — | 0 | **0** |

## Disabled mirrors

| Mirror | Country | Content age |
|--------|---------|------------:|
| liteserver.nl | 🇳🇱 NL | 1h |

\* *Scan = Mirrorbits indexing health (not in score). Reactivity = scan-duration proxy, not a measured download speed.*

