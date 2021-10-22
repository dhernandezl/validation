## Prerequisites
Go Hugo 0.80+ GNU Make 4+

# API
```
You should have a basic knowledge on the following concepts:

What a compiled language is (C/C#/Golang/Rust/etc.)

Generation process from source to executable binary
Basic types: string, integer, boolean, maps, arrays
Basic algorithmic: loops, conditional, functions
Installing command line tools with NPM (in addition to package managers)

Understand the basics of the HTTP protocol (client/server, verbs, headers)

Tooling
This project needs the following tools / services:

Same tools as previous module
Golang in v1.15.*
NPM v7+ with NodeJS v14.* (stable)
Python 3 with pip module
```

## Lifecycle
- lint 
```  
to execute a static analysis to lint this code 
```	
- go-build 
``` 
Compile the source code of the application to a binary
``` 
- hugo-build
```
creates website and locates it in the dist/ directory
```
- build
```
build hugo and API go
```
- run 
``` 
Run the application in background by executing the binary  
```
- clean
```
clean dist directory
```
- stop 
``` Stop the application ```
- post
```
acepts 2 parameters POST_NAME and POST_TITLE, the first one
gives the name of the post(without extension .md) and the
second one gives the title of the post. After this the post
will be created with command 'make POST_NAME POST_TITLE post'	
```
- check
```
- Lint of the Markdown source files using the command line "markdownlint-cli"
- Analysis of the links with the command line "markdown-link-check"
```
- validate
```
"Validate" should validate the file ./dist/index.html by using the command line Holberton's W3C Validator, but should not fail if the file is not valid: you expect it to be a non-blocking quality indicator.
```
- test 
```Test the application Unit Test - Integrations Test```
- unit-tests 
``` Unit testing with code coverage  ```
- integration-tests 
``` Integrations Test  ```
- help
```
command make help will gives a description of every command.	
```









