# CLAUDE.md

Этот файл содержит инструкции для Claude Code (claude.ai/code) при работе с данным репозиторием.

## О проекте

Лендинг кофейни «Кофеин» (Москва). Цель: превратить онлайн-посетителя в физического гостя через бронирование столика, прокладку маршрута или звонок. Основная аудитория — мобильные пользователи (80%+).

## Архитектура

Весь сайт — один файл **`index.html`**: весь CSS, HTML и JavaScript встроены inline. Без систем сборки, npm, JS-фреймворков и бандлеров. Для просмотра достаточно открыть `index.html` в браузере.

Ключевые дизайн-решения задокументированы в `brief.md` (техническое задание) и `research.md` (UX-исследование).

## Дизайн-токены

Все CSS-переменные объявлены в `:root` в начале `index.html`:
- Палитра: `--green`, `--beige`, `--terra` (терракотовый акцент)
- Типографика: Cormorant Garamond (заголовки, weight 300, `letter-spacing: -0.03em`) + DM Sans (текст) + DM Mono
- Лейаут: `--container: 1200px`, `--pad-section`, `--pad-x` используют `clamp()` для fluid-размеров

## Система анимаций

- `.reveal` / `.reveal-title` / `.reveal-left` / `.reveal-right` — появление при скролле через IntersectionObserver (JS в конце файла)
- Кастомный курсор (только десктоп, `@media (hover: hover) and (pointer: fine)`) — `.cursor-dot` + `.cursor-ring`
- Полоса прогресса скролла — `.scroll-progress` фиксирована сверху
- Бегущая рамка кнопки бронирования — CSS `@property --ba` с conic-gradient анимацией
- Ambient-свечение в Hero — CSS `@keyframes ambientDrift`

## Секции страницы (сверху вниз)

Nav → Hero → Features → Philosophy → Menu → Promotions → Amenities → Contact/Map → Footer

## Mobile-first

Все изменения лейаута должны работать на мобильном в первую очередь. По данным `brief.md`, 80%+ трафика — мобильный.
