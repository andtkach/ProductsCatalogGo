build:
	@go build -o bin/procago cmd/main.go

test:
	@go test -v ./...
	
run: build
	@./bin/procago

tidy:
	@go mod tidy

docker-up-db:
	@docker-compose up -d db

docker-up-all:
	@docker-compose up -d

docker-down:
	@docker-compose down

migration:
	@migrate create -ext sql -dir cmd/migrate/migrations $(filter-out $@,$(MAKECMDGOALS))

migrate-up:
	@go run cmd/migrate/main.go up

migrate-down:
	@go run cmd/migrate/main.go down
