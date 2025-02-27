# Инструкция по настройке Laravel-приложения в Docker

## 1. Клонирование репозитория
Сначала клонируйте репозиторий с помощью команды:

```bash
git clone https://github.com/eyekeen/test-task-blog && cd test-task-blog
```

```bash
cp .env.example .env
```

---

## 2. Сборка и запуск контейнеров
```bash
docker-compose up -d --build
```

---

## 3. Остальное
После запуска контейнеров установите зависимости Laravel внутри контейнера PHP:

```bash
docker-compose exec app bash
```

---

```bash
composer install && php artisan key:generate && php artisan migrate --seed
```

---

### 4. Даем права пользователю www-data
```
docker-compose exec app bash
```

```
chown www-data:www-data -R /var/www/html
```

---

Фронт: http://localhost:8080


phpmyadmin: http://localhost:8081

login: laraveluser
password: larapass

