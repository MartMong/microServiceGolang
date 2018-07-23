build:
	# protoc -I. --micro_out=$(GOPATH)/src/github.com/mart/vessel-service/ --go_out=plugins=grpc:$(GOPATH)/src/github.com/mart/vessel-service/ \
    # 	proto/vessel.proto
	sudo docker build -t vessel-service .

run:
	sudo docker run -p 50052:50051 -e MICRO_SERVER_ADDRESS=:50051 -e MICRO_REGISTRY=mdns vessel-service
