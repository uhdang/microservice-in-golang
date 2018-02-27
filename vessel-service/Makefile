build:
		protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/uhdang/microservice-in-golang/vessel-service \
			proto/vessel/vessel.proto
		docker build --no-cache -t vessel-service .

run:
		docker run --name c-vessel-service \
		-p 50052:50051 \
		-e MICRO_SERVER_ADDRESS=:50051 \
		-e MICRO_REGISTRY=mdns vessel-service
