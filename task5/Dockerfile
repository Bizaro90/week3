FROM golang:1.22 as builder

WORKDIR /mnt/c/Users/Bizaro/Documents/DEV-OPS_learning/Week3/kbot/task5
COPY . .
RUN make build

FROM scratch
WORKDIR /
COPY --from=builder /mnt/c/Users/Bizaro/Documents/DEV-OPS_learning/Week3/kbot/task5 .
COPY --from=alpine:latest /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/
ENTRYPOINT [ "./kbot" ]