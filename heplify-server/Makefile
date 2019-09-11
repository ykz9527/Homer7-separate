db=192.168.40.73
dbpass=homerSeven

pull:
	docker pull sipcapture/heplify-server:master;

run:
	docker run  \
	--name hepserver \
	--restart="always" \
	-p 9090:9090 \
	-p 9090:9090/udp \
	-m 1024m \
	-e HEPLIFYSERVER_DBDRIVER=postgres \
	-e HEPLIFYSERVER_HEPADDR=0.0.0.0:9060 \
	-e HEPLIFYSERVER_DBSHEMA=homer7 \
	-e HEPLIFYSERVER_DBADDR=$(db):5432 \
	-e HEPLIFYSERVER_DBUSER=postgres \
	-e HEPLIFYSERVER_DBPASS=$(dbpass) \
	-e HEPLIFYSERVER_DBDATATABLE=homer_data \
	-e HEPLIFYSERVER_LOGLVL=info \
	-e HEPLIFYSERVER_LOGSTD=true \
	-e HEPLIFYSERVER_PROMADDR=0.0.0.0:9096 \
	-e HEPLIFYSERVER_DBDROPDAYS=7 \
	-d -i sipcapture/heplify-server:master ./heplify-server

stop:
	docker rm -f hepserver
