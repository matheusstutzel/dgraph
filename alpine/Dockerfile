FROM dgraph/dgraph 

FROM alpine
RUN mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2
COPY --from=0 /usr/local/bin/dgraph /usr/local/bin/

RUN mkdir /dgraph
WORKDIR /dgraph
CMD ["dgraph"]