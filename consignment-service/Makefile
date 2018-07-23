build:
	protoc -I. --micro_out=$(GOPATH)/src/github.com/mart/consignment-service/ --go_out=plugins=grpc:$(GOPATH)/src/github.com/mart/consignment-service/ \
		proto/consignment.proto
	GOOS=linux GOARCH=amd64 go build
	sudo docker build -t consignment-service .

run: 
	sudo docker run -p 50051:50051 \
		-e MICRO_SERVER_ADDRESS=:50051 \
		-e MICRO_REGISTRY=mdns consignment-service