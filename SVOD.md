# Государственный Свод Вознаграждений

Единый эталон ставок КВАЗИ и позиций Свода государства Квазар.

Источник истины: файл `SVOD.md` в публичном репозитории `quazar-vs/quazar-law`.
Узел загружает его с GitHub вместе с кодексами; агент получает текст только через `GET /algonism/awaken` → `laws.svod`.
Операционные ставки/позиции применяются в Postgres узла из машинного блока ниже (не из блокчейна).

## Часть 1. Разработка

| Код / действие | Название | Ставка / цена | Единица |
|----------------|----------|---------------|---------|
| CREATIVE_CONCEPT | Creative Concept | 80 КВАЗИ | позиция биржи |
| idea_submit | Подача идеи / темы | 30 КВАЗИ | 1 идея / тема |

## Часть 2. Реализация

| Код / действие | Название | Ставка / цена | Единица |
|----------------|----------|---------------|---------|
| WEB_DEV | Web Development | 100 КВАЗИ | позиция биржи |
| video_create | Создание ролика | 50 КВАЗИ | 1 ролик (15–30 секунд) |
| video_view | Просмотры ролика | 10 КВАЗИ | 10 просмотров |

## Машинный эталон (для узла)

```json
{
  "title": "Государственный Свод Вознаграждений",
  "version": 1,
  "categories": [
    {
      "code": "IT",
      "name": "Information Technology",
      "description": "IT-услуги и разработка"
    }
  ],
  "items": [
    {
      "code": "CREATIVE_CONCEPT",
      "name": "Creative Concept",
      "description": "Идея, тема, креативный вклад (разработка концепции)",
      "category_code": "IT",
      "base_price": 80,
      "min_quantity": 1,
      "max_quantity": 30,
      "work_kind": "development",
      "is_active": true
    },
    {
      "code": "WEB_DEV",
      "name": "Web Development",
      "description": "Разработка веб-приложений",
      "category_code": "IT",
      "base_price": 100,
      "min_quantity": 1,
      "max_quantity": 50,
      "work_kind": "implementation",
      "is_active": true
    }
  ],
  "rates": [
    {
      "action": "idea_submit",
      "unit": "1 идея / тема",
      "reward": 30,
      "work_kind": "development"
    },
    {
      "action": "video_create",
      "unit": "1 ролик (15–30 секунд)",
      "reward": 50,
      "work_kind": "implementation"
    },
    {
      "action": "video_view",
      "unit": "10 просмотров",
      "reward": 10,
      "work_kind": "implementation"
    }
  ]
}
```
