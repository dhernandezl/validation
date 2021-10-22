lint: ## to execute a static analysis to lint this code.
	golangci-lint run

go-build: ## compiles the awesome-api application
	make lint
	go build

hugo-build: ## Construye una página estática con hugo y la guarda en dist
	hugo -D > /dev/null 2>&1

build: # Construye una página estática con hugo y la API Go
	make hugo-build
	make go-build

run: ## Run the application in background by executing the binary awesome-api, and write logs into a file named awesome.log with the command ./awesome-api >./awesome.log 2>&1 &.
	./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application. For instance: kill "$(pgrep awesome-api)".	killall awesome-api
	kill  $$(pgrep -f "awesome-api")

check: ## ## Debería fallar cuando falla uno de los 2 pasos siguientes: Lint de los archivos fuente de Markdown usando la línea de comando "markdownlint-cli" Análisis de los enlaces con la línea de comando "markdown-link-check" markdownlint / content / posts / * && markdown-link-check ./content/posts/* && echo 'SUCCESS' || echo 'FAIL' || echo 'FAIl'
	markdownlint ./content/posts/welcome.md > /dev/null 2>&1 && markdown-link-check -q ./content/posts/welcome.md >/dev/null 2>&1

.PHONY: clean
clean: ## Elimina el directorio dist en el directorio
	make stop > /dev/null 2>&1 &
	rm -rf ./awesome-api ./awesome.log ./coverage-units.out ./coverage-integrations.out ./dist/  > /dev/null 2>&1

post: ## Crea un nuevo post en la carpeta que esta configurada en config.toml acepta dos argumentos el nombre del archivo .md (POST_NAME sin la extension) y el titulo del post (POST_TITLE)
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2021/10/12 01:04 AM\ndraft: false\n---' > ./content/posts/$(POST_NAME).md
validate: ## "Validar" debe validar el archivo ./dist/index.html usando la línea de comando W3C Validator de Holberton, pero no debe fallar si el archivo no es válido: usted espera que sea un indicador de calidad sin bloqueo.
	/home/dhernandezl//W3C-Validator/w3c_validator.py ./dist/index.html > /dev/null 2>&1 || true;	

unit-tests: ## Unit testing with code coverage
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## executes the golang integrations tests
	go test -v -tags=integration -coverprofile=coverage-integrations.out

test: ## executes unit-tests and integrations-tests
	make unit-tests && make integration-tests

help: ## Muestra una breve descripción de todos los comandos
	grep '##' ./Makefile | sed 's/ ##/ /' | head -n -1
