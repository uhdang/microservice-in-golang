build:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/uhdang/microservice-in-golang/consignment-service \
	  proto/consignment/consignment.proto
	docker build --no-cache -t consignment-service .
run:
	docker run -p 50051:50051 \
		--name c-server \
		-e MICRO_SERVER_ADDRESS=:50051 \
		-e MICRO_REGISTRY=mdns consignment-service
