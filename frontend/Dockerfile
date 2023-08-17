FROM golang:1.21.0 as BUILD

WORKDIR /app

COPY . .

RUN CGO_ENABLED=0 go build -a -o main

#Runtime
FROM scratch
WORKDIR /app

COPY --from=BUILD /app/static/ /app/static/.
COPY --from=BUILD /app/templates/ /app/templates/.
COPY --from=BUILD /app/main /app/.
EXPOSE 8080

CMD ["./main"]