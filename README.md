# 🛑 Ultimate Blocklist by fenix_vd

Объединённый список доменов для **DNS-фильтрации** (AdGuard Home, Technitium DNS, Pi-hole).
Собирается автоматически из фильтров uBlock Origin и hosts-списков.

## 📋 Статистика

| 🕒 Последнее обновление | ``2026-09-01 00:00``   |
| 🔢 Всего доменов       | ``328528``  |
| 🆕 Новых за сутки      | ``1050``    |
| 🗑️ Удалённых           | ``1309``|

---

## ✅ Источники

**Набор uBlock Origin:**
- uBlock filters — Ads, Badware risks, Privacy, Quick fixes, Unbreak
- EasyList
- AdGuard — Ads
- EasyPrivacy
- Online Malicious URL Blocklist (urlhaus)
- Peter Lowe’s Ad and tracking server list
- AdGuard — Russian filter
- RU AdList: Counters

**Hosts-списки:**
- Schakal.ru

## ⚙️ Как это собирается

Списки для браузерных блокировщиков содержат правила, которые DNS-резолвер понять не может:
косметические (`##`, `#?#`), правила с модификаторами (`$popup`, `$csp`, `$third-party`),
regex- и path-правила. Если вывалить их в DNS-блоклист как есть, резолвер воспримет
перечисленные в них домены как подлежащие блокировке — и заблокирует тысячи нормальных сайтов.

Поэтому парсер берёт **только** hosts-записи и чистые сетевые правила вида `||domain^`,
всё остальное отбрасывает. Каждый домен проходит валидацию и проверку TLD.
Дополнительно вычитается собственный allowlist.

Сборка отменяется, если список внезапно уменьшился более чем вдвое или источник
отдал HTML вместо данных.

## 📥 Как использовать

Добавь фильтр по ссылке:

```
https://raw.githubusercontent.com/fenixvd/ultimate-blocklist/refs/heads/main/blocklist.txt
```

## 🕒 Обновление

Ежедневно, автоматически через cron.

## 🤖 Автор

[fenixvd](https://github.com/fenixvd)
