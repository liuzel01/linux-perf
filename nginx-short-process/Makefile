.PHONY: run
run:
	docker run --name nginx -p 10000:80 -itd lzl/nginx:sp
	docker run --name phpfpm -itd --network container:nginx lzl/php-fpm:sp

.PHONY: build
build:
	docker build -t lzl/nginx:sp -f Dockerfile.nginx .
	docker build -t lzl/php-fpm:sp -f Dockerfile.php-fpm .

.PHONY: push
push:
	docker push lzl/nginx:sp
	docker push lzl/php-fpm:sp

.PHONY: clean
clean:
	docker rm -f nginx phpfpm  || echo "Container nginx already deleted."
