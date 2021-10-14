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
- help
```
command make help will gives a description of every command.	
```

