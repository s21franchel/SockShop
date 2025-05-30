
# 🧦 SockShop - Интернет-магазин носков

Проект базы данных для интернет-магазина носков с полным циклом: от концептуальной модели до физической реализации.

## 📌 Особенности
- Полноценная ER-диаграмма
- 3 уровня проектирования БД (концептуальный, логический, физический)
- Готовые SQL-запросы для создания таблиц
- Примеры рабочих запросов для интернет-магазина

## 🛠 Технологии
- PostgreSQL (основная СУБД)
- SQL-нормализация (3NF)
- Индексы и оптимизация

## 🗂 Структура проекта
```
sockshop/
├── docs/
│   ├── erd-diagram.png       # ER-диаграмма
│   └── requirements.md       # Бизнес-требования
├── sql/
│   ├── 01_tables.sql         # Создание таблиц
│   ├── 02_indexes.sql        # Оптимизация
│   └── 03_sample_data.sql    # Тестовые данные
└── README.md
```

## 🚀 Быстрый старт
1. Создайте БД PostgreSQL:
```bash
createdb sockshop
```
2. Импортируйте схему:
```bash
psql sockshop < sql/01_tables.sql
```

## 📊 Примеры запросов
```sql
-- Топ-5 самых популярных носков
SELECT s.name, COUNT(o.sock_id) AS sales
FROM socks s
JOIN order_items o ON s.id = o.sock_id
GROUP BY s.name
ORDER BY sales DESC
LIMIT 5;
```

## 📝 Лицензия
MIT License. Используйте свободно для своих проектов!
```

---

### **🔹 Дополнительные файлы для репозитория**
1. **`docs/erd-diagram.png`** — картинка с ER-диаграммой (можно сделать в [draw.io](https://app.diagrams.net/)).
2. **`sql/01_tables.sql`** — SQL-скрипт из вашего логического уровня.
3. **`.gitignore`** — чтобы не загружать служебные файлы:
```
*.bak
*.tmp
.DS_Store
```

---

### **🔹 Как оформить коммит**
```bash
git add .
git commit -m "feat: add database schema for SockShop"
git push origin main
```

---

### **🔹 Идеи для развития проекта**
Упомяните в README, что можно доработать:
- Веб-интерфейс на Python/Django
- API для мобильного приложения
- Аналитику продаж через Power BI
