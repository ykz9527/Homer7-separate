#	-v /root/init-user-db.sh:/docker-entrypoint-initdb.d/init-user-db.sh \	-v /root/postgres-data:/var/lib/postgresql/data \
password=homerSeven

init:
	make pull;
	make cp;
pull:
	docker pull postgres:11-alpine;
cp:
	cp init-user-db.sh /root/;

run:
	docker run  \
	--name dbserver \
	-m 1024m \
	--restart="always" \
	-e POSTGRES_USER=postgres \
	-v /root/init-user-db.sh:/docker-entrypoint-initdb.d/init-user-db.sh \
	-v /root/postgres-data:/var/lib/postgresql/data \
	-e POSTGRES_PASSWORD=$(password) \
	-d -i -p 5432:5432 postgres:11-alpine;

stop:
	docker rm -f dbserver

logs:
	docker logs dbserver -f
