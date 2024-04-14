VERSION=$(shell date /T +%Y-%m-%d)- $(shell git rev-parse --short  HEAD)

format:
	gofmt -s -w ./
build: format
	CGO_ENABLED=0 GOOS=${TARGETOS} GOARCH=${shell dpkg --print-architecture} go build -v -o kbot.exe -ldflags="-X 'task5/cmd.appVerion=${VERSION}'"