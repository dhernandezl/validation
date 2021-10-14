build:
	hugo -D > /dev/null 2>&1

.PHONY: clean
clean: 
	rm -rf ./dist/ > /dev/null 2>&1

post:
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2021/10/12 01:04 AM\ndraft: false\n---' > ./content/posts/$(POST_NAME).md
