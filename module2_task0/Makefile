build: ##Compile the source
	go build

run:  ##Run the application in background
	./awesome-api >./awesome.log 2>&1 &

stop:	##Stop the application
	kill $(pgrep -f "awesome-api") > /dev/null 2>&1 &

.PHONY: clean
clean:  ##Delete the binary and the log
	make stop > /dev/null 2>&1 &
	rm -rf ./awesome-api ./awsome-api.log > /dev/null 2>&1 &

test: ##Test the application
	curl http://localhost:9999
	curl http://localhost:9999/health

help: ##gives a description of every command
	grep '##' ./Makefile | sed 's/ ##/ /' | head -n -1
