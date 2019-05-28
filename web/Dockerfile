FROM golang:alpine
COPY . .
RUN go build dispatcher.go
FROM alpine
COPY --from=0 /go/dispatcher .
COPY static static
CMD ["./dispatcher"]

