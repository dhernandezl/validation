build: ##Compile the source
	go build

run:  ##Run the application in background
	./awesome-api >./awesome.log 2>&1 &

stop:	##Stop the application
	kill "$(pgrep awesome-api)"

.PHONY: clean
clean:  ##Delete the binary and the log
	rm -r awesome-api
	rm awsome-api.log

test: ##Test the application
	curl http://localhost:9999
	curl http://localhost:9999/health

help: ##gives a description of every command
	grep '##' ./Makefile | sed 's/ ##/ /' | head -n -1
