VERSION=$(shell date /T +%Y-%m-%d)- $(shell git rev-parse --short  HEAD)

format:
	gofmt -s -w ./

lint:
	golint

test:
	go test -v

build: format
	go build -v -o kbot.exe -ldflags="-X 'task5/cmd.appVerion=${VERSION}'"

clean:
	del .\kbot.exe