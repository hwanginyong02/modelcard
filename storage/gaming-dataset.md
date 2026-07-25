---
configs:
- config_name: default
  data_files:
  - split: train
    path: metadata.jsonl
---

# Gaming Dataset (gaming-1) — 494.7 Hours

Native PC/console gameplay screen-recordings, organized **by game**. Each workflow
is one play session, trimmed to **pure gameplay** — login screens, launchers,
desktop, collection-app references, and any watching/streaming are removed.
In-game menus, lobbies, loading, and cutscenes are retained as part of the session.

- **Workflows:** 776
- **Total gameplay:** 494.7 hours
- **Distinct games:** 168
- **Clip duration (min):** median 24.0, p90 90.9, max 457.7
- **Platforms:** windows (489.3h), macos (5.3h)
- **Video:** 30fps CFR H.264.

## Layout
```
{game-slug}/{workflow_id}/
  clip.mp4           # gameplay-only, 30fps CFR
  events.json        # input/app events, rebased to the clip timeline (NDJSON)
  frame_events.json  # per-frame event view (NDJSON)
  metadata.json      # workflow_id, game, category, platform, title, description, tags, total_duration_ms, event_count
```

## Top games by hours
| Game | Workflows | Hours | Share |
|---|--:|--:|--:|
| Valorant | 117 | 102.2 | 20.7% |
| Minecraft | 75 | 41.3 | 8.3% |
| Grand Theft Auto V | 42 | 34.7 | 7.0% |
| Palworld | 30 | 28.7 | 5.8% |
| Assassins Creed Syndicate | 10 | 17.9 | 3.6% |
| 007 First Light | 13 | 17.5 | 3.5% |
| Age of Empires | 7 | 15.5 | 3.1% |
| Assassins Creed | 11 | 15.2 | 3.1% |
| Forza Horizon | 36 | 15.1 | 3.1% |
| Counter-Strike 2 | 20 | 12.2 | 2.5% |
| Asphalt 9 | 20 | 11.2 | 2.3% |
| Hitman 3 | 7 | 9.9 | 2.0% |
| Rocket League | 14 | 7.7 | 1.6% |
| Need for Speed | 11 | 6.9 | 1.4% |
| The Finals | 8 | 6.3 | 1.3% |
| Road 96 | 2 | 5.6 | 1.1% |
| Pragmata | 11 | 5.3 | 1.1% |
| Candy Crush | 13 | 5.2 | 1.1% |
| Dota 2 | 13 | 4.8 | 1.0% |
| Farming Simulator | 5 | 4.7 | 0.9% |
| Forza Horizon 3 | 5 | 3.8 | 0.8% |
| Wolfenstein | 4 | 3.8 | 0.8% |
| Ghost of Tsushima | 9 | 3.5 | 0.7% |
| PUBG/BGMI | 7 | 3.3 | 0.7% |
| Hogwarts Legacy | 4 | 2.8 | 0.6% |
