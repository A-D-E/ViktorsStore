# Використовуємо офіційне зображення Python як базовий образ
FROM python:3.12.3

# Встановлюємо пакети системних залежностей, якщо потрібно
RUN apt-get update && apt-get install -y postgresql-client

# Встановлюємо робочу директорію в /app
WORKDIR /app

# Створюємо віртуальне середовище і активуємо його
RUN python -m venv venv
ENV PATH="/app/venv/bin:$PATH"

# Копіюємо файли проекту в контейнер
COPY . .

# Встановлюємо залежності з requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Вказуємо команду для запуску бота або сервера Django
CMD ["sh", "-c", ". venv/bin/activate && python manage.py runserver 0.0.0.0:8001"]
