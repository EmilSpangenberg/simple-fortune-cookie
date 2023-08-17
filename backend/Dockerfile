FROM golang:1.21.0-alpine3.18
WORKDIR /app
COPY . .
RUN go build -o main .

FROM scratch
COPY --from=0 /app/main .
CMD ["./main"]