---
title: Mirror reliability status
description: Auto-generated mirror reliability ranking (do not edit by hand)
published: true
date: 2026-07-04T05:39:32.000Z
tags: documentation
editor: markdown
dateCreated: 2026-07-04T00:00:00.000Z
---

# Mirror reliability status

> **Auto-generated** page — data as of **2026-07-04 05:39 UTC**, over a rolling **30-day** window. Do not edit by hand: it is fully regenerated on a schedule. {.is-info}

This ranking is computed automatically from **Mirrorbits** health data — it is not a manual, editorial judgement. Mirrors are ordered by a transparent score:

`score = 0.5 × availability% + 0.3 × scan-success% + 0.2 × freshness`

- **Availability** — share of the window the mirror was reachable (Mirrorbits up/down).
- **Scan success** — share of Mirrorbits sync scans that completed without error.
- **Sync age** — time since the last *successful* content sync (lower is better; a mirror can be "up" yet serve stale content).
- **Reactivity** — *approximate* proxy only: median duration of successful scans. Mirrorbits does not measure real download speed/latency.
- **Downloads** — client requests / bytes served over the window (popularity, for context).

| # | Mirror | Country | State | Sync age | Avail. | Scan OK | Reactivity* | Downloads | Score |
|---|--------|---------|-------|---------:|-------:|--------:|------------:|----------:|------:|
| 1 | ufpr.br | 🇧🇷 BR | 🟢 up | 3h | 100.0% | 100% | 53s | 73 101 / 100.6 Go | **100** |
| 2 | icm.edu.pl | 🇵🇱 PL | 🟢 up | 1h | 100.0% | 100% | 56s | 44 066 / 53.0 Go | **100** |
| 3 | rpmfind.net | 🇫🇷 FR | 🟢 up | 3h | 100.0% | 100% | 29s | 129 787 / 129.9 Go | **100** |
| 4 | mirror-services.net | 🇧🇪 BE | 🟢 up | 0min | 100.0% | 100% | 25s | 106 544 / 101.6 Go | **100** |
| 5 | freedif.org | 🇸🇬 SG | 🟢 up | 1h | 100.0% | 100% | 31s | 66 904 / 87.7 Go | **100** |
| 6 | tu-chemnitz.de | 🇩🇪 DE | 🟢 up | 1h | 100.0% | 99% | 73s | 50 839 / 62.2 Go | **100** |
| 7 | yandex.ru | 🇷🇺 RU | 🟢 up | 0min | 100.0% | 99% | 81s | 11 820 / 14.9 Go | **100** |
| 8 | mirrorservice.org | 🇬🇧 GB | 🟢 up | 5h | 100.0% | 97% | 86s | 13 112 / 16.7 Go | **99** |
| 9 | hs-esslingen.de | 🇩🇪 DE | 🟢 up | 11h | 100.0% | 88% | 38s | 12 345 / 15.8 Go | **96** |
| 10 | openmandriva.org | 🇺🇸 US | 🟢 up | 23min | 100.0% | 7% | 149s | 112 874 / 120.4 Go | **72** |
| 11 | ibiblio.org | 🇺🇸 US | 🟢 up | 121j | 100.0% | 0% | — | 227 159 / 204.1 Go | **50** |
| 12 | accum.se | 🇸🇪 SE | 🔴 down | 6h | 1.7% | 84% | 333s | 85 147 / 81.9 Go | **46** |
| 13 | rise.ph | 🇵🇭 PH | 🔴 down | ? | 0.0% | 0% | — | 0 | **0** |
| 14 | hostafrica.co.za | 🇿🇦 ZA | 🔴 down | ? | 0.0% | 0% | — | 0 | **0** |
| 15 | northrepo.ca |   | 🔴 down | ? | 0.0% | 0% | — | 0 | **0** |
| 16 | remi.lu | 🇫🇷 FR | 🔴 down | 564j | 0.0% | 0% | — | 0 | **0** |
| 17 | garr.it | 🇮🇹 IT | 🔴 down | ? | 0.0% | 0% | — | 0 | **0** |

## Disabled mirrors

| Mirror | Country | Sync age |
|--------|---------|---------:|
| liteserver.nl | 🇳🇱 NL | 146j |

\* *Reactivity is an approximation (scan duration), not a measured download speed.*

