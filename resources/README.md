# Полезные ресурсы для Go-разработчиков

> 📚 [Добавить подборку профильных Telegram-каналов одним кликом](https://t.me/addlist/MUtJEeJSxeY2YTFi) · [Golang на русском](https://t.me/Golang_google)

Каталог для изучения Go с нуля, подготовки к собеседованиям и разработки backend-сервисов в production. Сначала изучайте стандартную библиотеку, затем выбирайте инструмент под конкретную задачу.

## Язык и фундамент

| Ресурс | Зачем читать |
|---|---|
| [A Tour of Go](https://go.dev/tour/) | Интерактивное знакомство с языком |
| [Go by Example](https://gobyexample.com/) | Короткие примеры синтаксиса и идиом |
| [Go Specification](https://go.dev/ref/spec) | Точная семантика языка |
| [Effective Go](https://go.dev/doc/effective_go) | Базовые идиомы |
| [Go Memory Model](https://go.dev/ref/mem) | Happens-before и синхронизация |
| [Go Blog](https://go.dev/blog/) | Объяснения от команды языка |
| [Go Wiki](https://go.dev/wiki/) | Практические материалы сообщества |
| [pkg.go.dev](https://pkg.go.dev/) | Документация пакетов |
| [Go Playground](https://go.dev/play/) | Быстрые эксперименты с кодом |
| [Learn Go with Tests](https://quii.gitbook.io/learn-go-with-tests) | Обучение через тестирование |
| [Go 101](https://go101.org/) | Подробности типов, памяти и runtime |

## Библиотеки для backend

| Задача | Инструменты |
|---|---|
| HTTP | [net/http](https://pkg.go.dev/net/http), [chi](https://github.com/go-chi/chi), [Gin](https://github.com/gin-gonic/gin) |
| gRPC | [grpc-go](https://github.com/grpc/grpc-go), [Connect](https://connectrpc.com/) |
| PostgreSQL | [pgx](https://github.com/jackc/pgx), [sqlc](https://sqlc.dev/) |
| Миграции | [goose](https://github.com/pressly/goose), [golang-migrate](https://github.com/golang-migrate/migrate) |
| Redis | [go-redis](https://github.com/redis/go-redis) |
| CLI | [Cobra](https://github.com/spf13/cobra) |
| Конкурентность | [errgroup](https://pkg.go.dev/golang.org/x/sync/errgroup), [singleflight](https://pkg.go.dev/golang.org/x/sync/singleflight) |
| Логирование | [log/slog](https://pkg.go.dev/log/slog), [zap](https://github.com/uber-go/zap) |
| Метрики | [Prometheus client](https://github.com/prometheus/client_golang) |
| Трейсинг | [OpenTelemetry Go](https://opentelemetry.io/docs/languages/go/) |
| Тесты | [testing](https://pkg.go.dev/testing), [testcontainers-go](https://github.com/testcontainers/testcontainers-go), [testify](https://github.com/stretchr/testify) |
| Генерация API | [oapi-codegen](https://github.com/oapi-codegen/oapi-codegen) |

## Инструменты ежедневной работы

- [gopls](https://go.dev/gopls/) — языковой сервер.
- [Staticcheck](https://staticcheck.dev/) — статический анализ.
- [golangci-lint](https://golangci-lint.run/) — набор линтеров.
- [Delve](https://github.com/go-delve/delve) — отладчик.
- [benchstat](https://pkg.go.dev/golang.org/x/perf/cmd/benchstat) — статистическое сравнение benchmark.
- [Go diagnostics](https://go.dev/doc/diagnostics) — профилирование и диагностика.
- [Go release notes](https://go.dev/doc/devel/release) — изменения языка и toolchain.

## Шпаргалка команд

```bash
go version
go env GOMOD
go mod tidy
go fmt ./...
go vet ./...
go test ./...
go test -race ./...
go test -coverprofile=coverage.out ./...
go tool cover -html=coverage.out
go test -run='^$' -bench=. -benchmem -count=10 ./...
go build ./...
```

## Roadmap: от Junior до Senior

| Уровень | Темы | Практический результат |
|---|---|---|
| Junior | Типы, slices, maps, interfaces, ошибки, modules, тесты | CLI для чтения CSV с тестами |
| Middle | Context, goroutines, HTTP, SQL, транзакции, Docker, CI | REST API с PostgreSQL и интеграционными тестами |
| Senior | Архитектура, backpressure, профилирование, SLO, миграции, надежность | Сервис с очередью, метриками и документированными компромиссами |

## Практические задачи

1. CLI: импортировать CSV, проверить данные, вывести агрегаты, покрыть крайние случаи тестами.
2. REST API: каталог книг с pagination, валидацией и graceful shutdown. Проверить HTTP-контракт через httptest.
3. Worker pool: ограничить параллелизм, поддержать отмену context, проверить корректное завершение при ошибках.
4. PostgreSQL: модель заказов с транзакциями, миграциями и интеграционными тестами.
5. Оптимизация: написать два варианта агрегатора, сравнить ns/op, B/op и allocs/op, объяснить результат.
6. Наблюдаемость: добавить структурированные логи, метрики длительности запросов и количество ошибок; описать SLO и план диагностики.

## Подготовка к собеседованию

- Чем slice отличается от array? Почему append иногда меняет backing array?
- Почему interface с типизированным nil может не равняться nil?
- Когда нужен mutex, а когда channel? Что гарантирует модель памяти?
- Как правильно отменить работу goroutine?
- Как избежать долгих транзакций и исчерпания пула PostgreSQL?
- Чем отличается CPU-профиль от heap-профиля?
- Как проверить, что повтор запроса не создаст дубликаты?
- Когда выделять интерфейс, а когда оставить конкретный тип?

Хороший ответ содержит пример, ограничения и способ проверить гипотезу, а не только определение.

[Вернуться к Agent Skills](../README.md)
