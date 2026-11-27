# База знаний: fedorlushnikov.com

Всё, что нужно знать, чтобы править и поддерживать сайт. Обновляется вместе с правками (см. `CLAUDE.md`).
История изменений — в [ACTIVITY.md](ACTIVITY.md).

## Коротко
- **Что это:** личный сайт Fedor Lushnikov (англоязычный, для поступления: Computer Science, fall 2027).
- **Адрес:** https://fedorlushnikov.com (и www).
- **Репозиторий:** https://github.com/Frininww/fedorlushnikov.com (публичный — не храните здесь пароли и личные данные).
- **Владелец:** аккаунт GitHub `Frininww` (с 2026-11-24; до этого `LevAvdoshin`).

## Устройство репозитория
| Путь | Что там |
|---|---|
| `site/index.html` | Весь сайт: разметка, CSS и JS в одном файле |
| `site/img/` | Фото в `.webp` (hero, игрок, проекты, фон) |
| `site/fonts/` | Шрифты woff2: Anton, Inter, Space Grotesk |
| `site/CNAME` | Домен для GitHub Pages |
| `site/.nojekyll` | Отключает Jekyll на Pages |
| `site/favicon*`, `apple-touch-icon.png` | Иконки |
| `.github/workflows/pages.yml` | Деплой на GitHub Pages |
| `docs/` | Журнал и база знаний (на сайт не попадает) |

## Секции страницы (`site/index.html`)
| id / класс | Содержание |
|---|---|
| `header.hero#top` | Имя, фото, цитата из эссе, карточки «Serenity & LockedIn» и «Next up: Moscow → USA» (Fall 2027, Computer Science BS, Class of 2031) |
| `.bands` | Бегущие ленты Build / Train / Focus… |
| `section.stats` | Плитки с цифрами: 1300+ игр LockedIn, 3 года PSG Academy, All A's |
| `.orgs` | Лента логотипов: PSG Academy, Cambridge, TOEFL, UWEE, Kid Castle, Skolkovo |
| `#story` | «Short of breath, then Player of the Month.» + доска задач и таймлайн |
| `#projects` | «Tools I built for real people»: Serenity, бот, LockedIn |
| `#pitch` | «Soccer taught me discipline» |
| `#beyond` | «Beyond the code: Music, teaching and travel». Карточки `.news-item`: Skolkovo Innovation Center (первая, широкая `.wide`), Choir «Rondo», Teaching English, Belt and Road Camp, Olympiad, Event volunteer, KidsDev |
| `#academics` | «School record»: оценки, TOEFL 100, Cambridge, олимпиада, KidsDev |
| `footer#contact` | Контакты и форма |

Числа в плитках анимируются через класс `.count.cNNN{--to:NNN}` (CSS-переменная с целевым значением).
Иконки — SVG-символы `<symbol id="i-…">` в начале body, логотипы — `<symbol id="o-…">`.

## Хостинг и деплой
- GitHub Pages, тип сборки «workflow». Публикуется папка `site/` как есть.
- Деплой: любой push в `main`, затрагивающий `site/**` или `pages.yml`, — сайт обновляется ~за минуту. Можно запустить вручную: `gh workflow run pages.yml`.
- Проверить статус: `gh run list --limit 3`.
- HTTPS принудительный, сертификат Let's Encrypt через GitHub (обновляется автоматически).
- DNS домена указывает на GitHub Pages.

## Почта и форма
- `hello@fedorlushnikov.com` — адрес на сайте (mailto), работает как раньше.
- Форма в футере: `POST https://formsubmit.co/<gmail Фёдора>`, после отправки редирект на `/?form=sent#sent`. Сервера нет.
- formsubmit требует один раз подтвердить адрес (письмо активации на Gmail).

## Как править
1. `git clone https://github.com/Frininww/fedorlushnikov.com` и открыть папку в `claude`.
2. Попросить правку, проверить `site/index.html` в браузере (десктоп и узкий экран).
3. Записать правку в `docs/ACTIVITY.md` (Claude делает это сам по `CLAUDE.md`).
4. Через PR или push в `main` — сайт обновится сам.

## Ссылки на проекты
- Serenity: https://serenityapps.online
- Telegram-бот: https://t.me/HealthScheduled_Bot

## Решения и договорённости
- 2026-11-27: год выпуска — Class of 2031 (поступление Fall 2027).
- 2026-11-27: Инновационный центр Сколково — отдельная карточка в «Beyond the code», помимо KidsDev.
- 2026-11-24: убраны все упоминания числа пользователей бота («27») и плавающие плашки в hero — не показывать эти цифры на сайте.
- 2026-11-24: хостинг — GitHub Pages вместо AWS S3 (проще, бесплатно, деплой из `main`).
