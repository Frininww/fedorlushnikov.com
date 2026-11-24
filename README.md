# Client-Fedor-Lushnikov

Сайт-био клиента Global Generation Фёдора Лушникова: **https://fedorlushnikov.com** (поступление в США, Computer Science, Fall 2027).

- Код сайта: `site/` (один `index.html`, картинки `site/img/`, шрифты `site/fonts/`). Сайт на английском.
- Хостинг: S3 `fedorlushnikov-site-818034793268` + CloudFront `E2QUX3F37GPA88` (AWS 818034793268, us-east-1).
- Деплой: push в `main` → GitHub Actions `deploy.yml` (OIDC-роль `github-actions-client-fedor-lushnikov-deploy`, только этот бакет и эта раздача) → проверка, что прод совпадает с `main`. В `main` только по «Деплой» Льва.
- Почта: hello@fedorlushnikov.com принимает SES и пересылает Фёдору (Lambda `fedorlushnikov-inbound-forward`, копия в S3 `gg-inbound-mail-818034793268/fedorlushnikov/`).

## Правила правок
- Правки присылает Фёдор в чат «Федор | Global Gen»; разбираются раз в день, одним PR.
- Только факты, которые Фёдор сам подтвердил в чате или которые есть на его сайтах (serenityapps.online и т.п.). Цифры, награды, имена не придумывать.
- Без длинного тире. Фото людей только настоящие, от Фёдора.
- Перед PR скрин страницы (десктоп 1440 и телефон 390).
