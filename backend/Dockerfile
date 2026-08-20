FROM python:3.12

WORKDIR /app

# Устанавливаем Gunicorn до копирования остального кода (для кэширования)
RUN pip install gunicorn==25.3.0

# Копируем зависимости и устанавливаем их
COPY requirements.txt .
RUN pip install -r requirements.txt --no-cache-dir

# Копируем весь проект
COPY . .

# Запускаем Gunicorn вместо runserver
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]