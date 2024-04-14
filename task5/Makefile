VERSION=$(shell date /T +%Y-%m-%d)- $(shell git rev-parse --short  HEAD)
TARGETOS=linux
format:
	gofmt -s -w ./

lint:
	golint

test:
	go test -v

build: format
	set CGO_ENABLED=0&& set GOOS=${TARGETOS}&& set GOARCH=${env:PROCESSOR_ARCHITECTURE}&& go build -v -o kbot.exe -ldflags="-X 'task5/cmd.appVerion=${VERSION}'"

clean:
	del .\kbot.exe