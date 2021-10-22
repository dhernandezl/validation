build: ## Construye una página estática con hugo y la guarda en dist
	hugo -D > /dev/null 2>&1

check: ## ## Debería fallar cuando falla uno de los 2 pasos siguientes: Lint de los archivos fuente de Markdown usando la línea de comando "markdownlint-cli" Análisis de los enlaces con la línea de comando "markdown-link-check" markdownlint / content / posts / * && markdown-link-check ./content/posts/* && echo 'SUCCESS' || echo 'FAIL' || echo 'FAIl'
	markdownlint ./content/posts/welcome.md > /dev/null 2>&1 && markdown-link-check -q ./content/posts/welcome.md >/dev/null 2>&1

.PHONY: clean
clean: ## Elimina el directorio dist en el directorio
	rm -rf ./dist/ > /dev/null 2>&1

post: ## Crea un nuevo post en la carpeta que esta configurada en config.toml acepta dos argumentos el nombre del archivo .md (POST_NAME sin la extension) y el titulo del post (POST_TITLE)
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2021/10/12 01:04 AM\ndraft: false\n---' > ./content/posts/$(POST_NAME).md
validate: ## "Validar" debe validar el archivo ./dist/index.html usando la línea de comando W3C Validator de Holberton, pero no debe fallar si el archivo no es válido: usted espera que sea un indicador de calidad sin bloqueo.
	/home/dhernandezl//W3C-Validator/w3c_validator.py ./dist/index.html > /dev/null 2>&1 || true;	

help: ## Muestra una breve descripción de todos los comandos
	grep '##' ./Makefile | sed 's/ ##/ /' | head -n -1
