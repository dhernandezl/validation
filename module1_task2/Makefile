build: ## Construye una página estática con hugo y la guarda en dist
	hugo -D > /dev/null 2>&1

.PHONY: clean
clean: ## Elimina el directorio dist en el directorio
	rm -rf ./dist/ > /dev/null 2>&1

post: ## Crea un nuevo post en la carpeta que esta configurada en config.toml acepta dos argumentos el nombre del archivo .md (POST_NAME sin la extension) y el titulo del post (POST_TITLE)
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2021/10/12 01:04 AM\ndraft: false\n---' > ./content/posts/$(POST_NAME).md
help: ## Muestra una breve descripción de todos los comandos
	grep '##' ./Makefile | sed 's/ ##/ /' | head -n -1
