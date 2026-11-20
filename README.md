cat > README.md << 'EOF'
# Cloud Container Demo

Небольшой Flask-сервис проверки состояния, упакованный в Docker и развернутый на Render.

## Маршруты
- `/` — JSON с названием приложения, версией и именем студента
- `/health` — `{"status": "ok"}` с кодом 200

## Локальный запуск
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

## Запуск в Docker
```bash
docker build -t cloud-container-app:1.0 .
docker run --rm -p 10000:10000 --name cloud-demo cloud-container-app:1.0
```

## Переменные окружения
- `PORT` — порт приложения (по умолчанию 10000)

## Облачный деплой
Приложение развернуто на Render как Web Service (Docker, тариф Free):
https://qo3e9g6i76.onrender.com/
EOF