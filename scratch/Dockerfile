FROM matheusstutzel/go-cross
RUN go get -u -v github.com/dgraph-io/dgraph/dgraph
WORKDIR /gopath/src/github.com/dgraph-io/dgraph/dgraph
RUN CGO_ENABLED=1 GOOS=linux GOARCH=amd64 go build -a -tags netgo -ldflags '-w -extldflags "-static"' .


FROM scratch
WORKDIR /
COPY --from=0 /gopath/src/github.com/dgraph-io/dgraph/dgraph/dgraph .
CMD [ "./dgraph"]