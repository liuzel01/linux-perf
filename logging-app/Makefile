.PHONY: run
run:
	docker run -v /tmp:/tmp --name=app -itd lzl/logapp


.PHONY: build
build:
	docker build -t lzl/logapp -f Dockerfile .


.PHONY: push
push:
	docker push lzl/logapp


.PHONY: clean
clean:
	docker rm -f app || echo "Container app already deleted."
