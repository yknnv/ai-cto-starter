# Стартовый набор для внедрения ИИ в разработку

Репозиторий-шаблон к курсу [«Переход на разработку с ИИ»](https://ykononov.ru/ai-cto/). В нём готовая структура проекта: файл контекста для ИИ-агента, шаблоны документов внедрения, промпты курса и шаблон пул-реквеста с отметкой об участии ИИ.

Набор сделан под Claude Code, но не привязан к нему. Правила проекта лежат в `AGENTS.md`, промпты записаны обычными Markdown-файлами, поэтому с ними работает любой агент и любой чат с моделью.

## Как начать

1. Нажмите **Use this template** вверху страницы и создайте свой репозиторий. Либо скопируйте нужные папки в существующий проект.
2. Заполните `AGENTS.md`: это файл, который агент читает перед работой. Проще всего сделать это с моделью по промпту [prompts/11-context.md](prompts/11-context.md).
3. Соберите первые документы в `docs/ai/`. Порядок описан в [docs/ai/README.md](docs/ai/README.md).
4. Перед первой задачей для агента напишите спецификацию в `specs/`.

Используйте модель, которую разрешила ваша служба ИБ. Не вставляйте в ответы секреты, персональные данные и код из закрытых систем.

## Что внутри

```
AGENTS.md                      файл контекста: что за проект и как в нём работать
CLAUDE.md                      подключает AGENTS.md для Claude Code
docs/ai/                       документы внедрения: политика, пилот, baseline, окупаемость и другие
docs/ai/examples/              пример заполненного файла контекста
specs/                         спецификации изменений, шаблон и пример
prompts/                       14 промптов курса: модель задаёт вопросы и собирает документ
evals/golden/                  набор эталонных задач для сравнения инструментов и моделей
.claude/commands/              команды Claude Code, которые запускают промпты из prompts/
.github/pull_request_template.md   пул-реквест с отметкой об участии ИИ
.github/copilot-instructions.md    отсылка к AGENTS.md для GitHub Copilot
```

## Промпты

| Документ | Промпт | В Claude Code |
| --- | --- | --- |
| 3 причины и метрика к каждой | [prompts/01-reasons.md](prompts/01-reasons.md) | `/reasons` |
| Выбранный уровень автономии и почему | [prompts/02-autonomy.md](prompts/02-autonomy.md) | `/autonomy` |
| Модель окупаемости на своих числах | [prompts/03-payback.md](prompts/03-payback.md) | `/payback` |
| Политика использования ИИ, 8 пунктов | [prompts/04-policy.md](prompts/04-policy.md) | `/policy` |
| Спецификация под свой проект | [prompts/05-spec.md](prompts/05-spec.md) | `/spec` |
| Список задач первой волны | [prompts/06-first-wave.md](prompts/06-first-wave.md) | `/first-wave` |
| Baseline: что снять до старта | [prompts/07-baseline.md](prompts/07-baseline.md) | `/baseline` |
| 3 риска для своей компании | [prompts/08-risks.md](prompts/08-risks.md) | `/risks` |
| Состав пилотной группы | [prompts/09-pilot-team.md](prompts/09-pilot-team.md) | `/pilot-team` |
| Дизайн пилота | [prompts/10-pilot.md](prompts/10-pilot.md) | `/pilot` |
| Файл контекста для репозитория | [prompts/11-context.md](prompts/11-context.md) | `/context` |
| Чек-лист для ИБ | [prompts/12-security-checklist.md](prompts/12-security-checklist.md) | `/security-checklist` |
| Вопросы вендорам | [prompts/13-vendor-questions.md](prompts/13-vendor-questions.md) | `/vendor-questions` |
| Чек-лист самооценки | [prompts/14-self-check.md](prompts/14-self-check.md) | `/self-check` |

## Если у вас другой агент

| Агент | Что сделать |
| --- | --- |
| Claude Code | Ничего: `CLAUDE.md` подключает `AGENTS.md`, команды лежат в `.claude/commands/` |
| Агент, который читает `AGENTS.md` | Ничего: файл лежит в корне |
| GitHub Copilot | Ничего: `.github/copilot-instructions.md` отсылает к `AGENTS.md` |
| Агент со своим файлом правил | Создайте его файл правил с одной строкой: «Правила проекта лежат в AGENTS.md, прочитай его перед работой» |
| Чат с моделью без доступа к репозиторию | Вставьте в чат содержимое `AGENTS.md` и нужного промпта |

Какие файлы читает ваш агент, проверьте в его документации: названия меняются от версии к версии. Команды из `.claude/commands/` другим агентам не нужны: попросите агента прочитать файл из `prompts/`.

## Что не входит в набор

- Сам код. Набор описывает правила и документы вокруг кода.
- Настройки шлюза, лимитов и журнала запросов: они зависят от инструмента. Что настроить, описано в [блоке 04](https://ykononov.ru/ai-cto/stoimost-tokenov-okupaemost/) и [блоке 05](https://ykononov.ru/ai-cto/bezopasnost-politika-ii/) курса.
- Готовые ответы. Шаблоны служат отправной точкой, подстраивайте их под свою компанию.

## Курс и автор

Курс бесплатный: [на сайте](https://ykononov.ru/ai-cto/), [в Телеграм-боте](https://t.me/ai_cto_course_bot) и [в репозитории на GitHub](https://github.com/yknnv/ai-cto-ru).

**Юрий Кононов** – CTO. Телеграм-канал: [@ykononovmd](https://t.me/ykononovmd), почта: [kononovpost@gmail.com](mailto:kononovpost@gmail.com).

Нашли неточность или есть предложение? Откройте issue в этом репозитории или напишите автору.

## Лицензия

[CC BY-NC 4.0](LICENSE.md): можно копировать и менять под свою компанию, нельзя продавать. Документы, которые вы создали по шаблонам, принадлежат вам.
