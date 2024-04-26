APP=$(shell basename $(shell git remote get-url origin))
REGISTRY=europe-central2-docker.pkg.dev/dev-ops-prometheus/week3
VERSION=$(shell date +%Y-%m-%d)-$(shell git rev-parse --short HEAD)
TARGETOS=linux
TARGETARCH=amd64
get:
	go get

format:
	gofmt -s -w ./

lint:
	golint

test:
	go test -v

build: format get
	CGO_ENABLED=0 GOOS=${TARGETOS} GOARCH=${TARGETARCH} go build -v -o kbot -ldflags="-X 'task5/cmd.appVerion=${VERSION}'"

image:
	docker build . -t ${REGISTRY}/${APP}:${VERSION}-${TARGETARCH}

push:
	docker push ${REGISTRY}/${APP}:${VERSION}-${TARGETARCH}

linux: 
	make TARGETOS=linux TARGETARCH=amd64 build

windows:
	make TARGETOS=windows TARGETARCH=amd64 build

arm:
	make TARGETOS=linux TARGETARCH=arm64 build

macos:
	make TARGETOS=darwin build

clean:
	docker rmi ${REGISTRY}/${APP}:${VERSION}-${TARGETARCH}; rm -rf kbot