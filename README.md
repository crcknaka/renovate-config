# renovate-config

Общий пресет Renovate для проектов SitesPro. В каждом репо — только

```json
{ "extends": ["github>crcknaka/renovate-config"] }
```

Правила (`default.json`):
- PR создаются в понедельник 03–07 по Риге; патчи — одним PR и сливаются сами пн 9–12 при зелёном CI,
  минорные — одним PR вручную, мажоры — только по галочке в Dependency Dashboard.
- Свежие релизы ждут 3 дня. Next и React — всегда вместе. Node в образах — только чётные LTS.
- Уязвимости: PR сразу, патч сливается сам в любой день 9–18 при зелёном CI.

Автослияние = выкат в прод (вебхук Coolify). План и решения — `SitesPro-Infra/docs/renovate.md`.
Проверка конфига: `npx --package renovate renovate-config-validator default.json`.
