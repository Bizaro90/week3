VERSION=$(shell date +%Y-%m-%d) - $(shell git rev-parse --short  HEAD)

get:
	go get

format:
	gofmt -s -w ./

lint:
	golint

test:
	go test -v

build: format
	CGO_ENABLED=0 GOOS=${TARGETOS} GOARCH=${shell dpkg --print-architecture} go build -v -o kbot -ldflags="-X 'task5/cmd.appVerion=${VERSION}'"

clean:
	rm -rf kbot