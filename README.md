# helloapi

Минимальный HTTP-сервис на Go (стандартная библиотека `net/http`).
Практическое занятие №1 по дисциплине «Технологии создания программного обеспечения».

## Возможности

- `GET /hello` — текстовый ответ `Hello, world!`
- `GET /user` — JSON-ответ с полем `id` (реальный UUID, библиотека `github.com/google/uuid`)
- `GET /health` — health-check: `{"status":"ok","time":"<RFC3339>"}`

## Требования

- Go 1.21+
- Git

## Запуск

```powershell
go run ./cmd/server
```

Сервер слушает порт `:8080` (по умолчанию).

## Сборка

```powershell
go build -o helloapi.exe ./cmd/server
.\helloapi.exe
```

## Конфигурация

Порт задаётся переменной окружения `APP_PORT` (по умолчанию `8080`):

```powershell
$env:APP_PORT="8081"
go run ./cmd/server
```

## Примеры запросов

```powershell
curl http://localhost:8080/hello
# Hello, world!

curl http://localhost:8080/user
# {"id":"3f1c1c5c-9a1b-4a6a-8a26-7b3f2f7d8b0b","name":"Gopher"}

curl http://localhost:8080/health
# {"status":"ok","time":"2026-11-04T12:00:00Z"}
```

## Структура проекта

```
helloapi/
  cmd/
    server/
      main.go
  go.mod
  go.sum
  README.md
```
