VERSION=$(shell date +%Y-%m-%d)- $(shell git rev-parse --short  HEAD)

format:
	gofmt -s -w ./

lint:
	go lint

test:
	go test -v

build: format
	CGO_ENABLED=0 GOOS111111=${TARGETOS} GOARCH1111=${shell dpkg --print-architecture} go build -v -o kbot -ldflags="-X 'task5/cmd.appVerion=${VERSION}'"

#	CGO_ENABLED=0 GOOS=${TARGETOS} GOARCH=${shell dpkg --print-architecture} go build -v -o kbot.exe -ldflags="-X 'task5/cmd.appVerion=${VERSION}'"
clean:
	rm -rf kbot