db=192.168.40.79
dbpass=homerSeven

init:
	make pull;
pull:
	docker pull sipcapture/homer-app:master;

run:
	docker run  \
	--name webserver \
	--restart="always" \
	-p 8002:80 \
	-m 1024m \
	-e DB_HOST=$(db) \
	-e DB_USER=postgres \
	-e DB_PASS=$(dbpass) \
	-d -i sipcapture/homer-app:master

stop:
	docker rm -f webserver

logs:
	docker logs webserver -f
