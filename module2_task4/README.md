## Prerequisites
Go Hugo 0.80+ GNU Make 4+

## Lifecycle
- build
```
creates website and locates it in the dist/ directory
```
- clean
```
clean dist directory
```
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
- help
```
command make help will gives a description of every command.	
```

