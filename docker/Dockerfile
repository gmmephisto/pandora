FROM golang:1.14 AS build

ENV GO111MODULE=on

WORKDIR /go/src/github.com/yandex/pandora
COPY . ./

RUN make build

FROM scratch
COPY --from=build /go/src/github.com/yandex/pandora/out/pandora /usr/local/bin/pandora

WORKDIR /pandora
ENTRYPOINT ["/usr/local/bin/pandora"]
