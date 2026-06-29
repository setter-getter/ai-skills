# ai-skills

Claude Code skills для QA/BA-команды проекта **Добро.РФ**. Переписаны из GitHub-агентов (`dobro-tests/.github/agents/*`) в формат Claude Code skills.

## Скиллы

| Скилл | Назначение | Зависимости |
|-------|-----------|-------------|
| [`allure-tc-manager`](allure-tc-manager/SKILL.md) | Управление тест-кейсами в Allure TestOps (проект Добро.РФ, ID 15): создание/редактирование TC, тест-планы, кастомные поля, статусы, bulk-операции | MCP `testops-local` |
| [`ba-formalize-task`](ba-formalize-task/SKILL.md) | Формализация сырой задачи (переписка/созвон/заметка) в атомарные карточки с критериями приёмки, тест-кейсами и открытыми вопросами | — |
| [`db-expert`](db-expert/SKILL.md) | Read-only эксперт по PostgreSQL: структура БД, связи, foreign keys, SELECT-запросы | MCP `postgres` |
| [`qa-task-intake`](qa-task-intake/SKILL.md) | QA-разбор задачи перед тестированием: тест-план, пробелы в требованиях, блокеры и вопросы | — |
| [`specs-search`](specs-search/SKILL.md) | Поиск и анализ требований из ЧТЗ Добро.РФ (`ai_docs/spec/`) с точными цитатами и источниками | — |

## Установка

Скиллы Claude Code подхватываются из директорий:
- **Проектные**: `.claude/skills/<name>/SKILL.md` в корне проекта
- **Пользовательские**: `~/.claude/skills/<name>/SKILL.md`

Чтобы подключить скилл из этого репозитория, скопируйте/симлинкните нужную директорию:

```bash
# пример: проектный скилл в dobro-tests
ln -s "$(pwd)/specs-search" ../dobro-tests/.claude/skills/specs-search

# или пользовательский (глобально)
ln -s "$(pwd)/allure-tc-manager" ~/.claude/skills/allure-tc-manager
```

После этого скилл доступен по имени через меню `/` или автоматически по описанию в `description`.

## Формат скилла

Каждый скилл — это директория с файлом `SKILL.md`:

```markdown
---
name: my-skill
description: Что делает скилл и когда его применять (Use when ...).
---

# Инструкции скилла...
```
