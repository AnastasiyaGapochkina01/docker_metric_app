# Metrics app
## Описание
Flask-приложение с эндпоинтом для мониторинга, а также с логированием запросов в PostgreSQL. Приложение позволяет собирать метрики HTTP-запросов, анализировать ошибки и время отклика, а также генерировать нагрузку для тестирования мониторинга.

## Возможности
Мониторинг HTTP-запросов: сбор количества запросов, ошибок и времени ответа.

Логирование в PostgreSQL: все запросы сохраняются в таблицу logs с деталями.

Интеграция с Prometheus и Grafana: удобный сбор и визуализация метрик.

Генерация нагрузки: специальный эндпоинт для тестирования мониторинга.

## Эндпоинты
```
curl http://localhost:5000/generate-load
curl http://localhost:5000/generate-load?n=5000000

curl http://localhost:5000//metrics
```

## Логи
Чтобы получить логи приложения используется подобный запрос в БД
```
SELECT * FROM logs WHERE endpoint = '/generate-load' ORDER BY timestamp DESC
```
