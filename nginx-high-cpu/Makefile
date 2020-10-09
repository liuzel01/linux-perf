.PHONY: run
run:
	docker run --name nginx -p 10000:80 -itd lzl/nginx:cpu
	docker run --name phpfpm -itd --network container:nginx lzl/php-fpm:cpu

.PHONY: build
build:
	docker build -t lzl/nginx:cpu -f Dockerfile.nginx .
	docker build -t lzl/php-fpm:cpu -f Dockerfile.php-fpm .

.PHONY: push
push:
	docker push lzl/nginx:cpu
	docker push lzl/php-fpm:cpu

.PHONY: clean
clean:
	docker rm -f nginx phpfpm || echo "Container nginx already deleted."
