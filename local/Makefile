.PHONY: start logs connect clean

start:
	@sudo docker-compose up --detach
	@echo
	@echo
	@echo "##############"
	@echo "# Connect to the DB"
	@echo "##############"
	@CONNECT_VAR=$$(docker port milvus-standalone 19530/tcp); \
	echo "To connect to the DB use the following: $${CONNECT_VAR}"

logs:
	@if [ -z "$(container)" ]; then \
		echo "Please provide a container name. Usage: make logs container=<CONTAINER_NAME>"; \
	else \
		docker logs $(container); \
	fi

connect:
	@docker port milvus-standalone 19530/tcp

clean:
	@sudo docker-compose down
	@sudo rm -rf volumes
