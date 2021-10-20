lint: ## to execute a static analysis to lint this code.
	golangci-lint run

build: ## compiles the awesome-api application
	make lint
	go build

run: ## Run the application in background by executing the binary awesome-api, and write logs into a file named awesome.log with the command ./awesome-api >./awesome.log 2>&1 &.
	./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application with the command kill XXXXX where XXXXX is the Process ID of the application. For instance: kill "$(pgrep awesome-api)".	killall awesome-api
	kill  $$(pgrep -f "awesome-api") > /dev/null 2>&1 &  

.PHONY : clean
clean: ## Delete the binary awesome-api and the log file awesome-api.log
	make stop > /dev/null 2>&1 &
	rm -rf ./awesome-api ./awesome.log ./coverage-units.out ./coverage-integrations.out  > /dev/null 2>&1

unit-tests: ## Unit testing with code coverage
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## executes the golang integrations tests
	go test -v -tags=integration -coverprofile=coverage-integrations.out

test: ## executes unit-tests and integrations-tests
	make unit-tests && make integrations-tests

help: ## gives a descriptios of every command
	grep '##' ./Makefile  | sed 's/ ##/ /' |  head -n -1
