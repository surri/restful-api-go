FROM golang:1.14.4

ADD . $GOPATH/src/
WORKDIR $GOPATH/src/

COPY go.mod .
COPY go.sum .

COPY . .

RUN go mod download

RUN go get -u "github.com/gin-gonic/contrib/cors"
RUN go get -u "github.com/codegangsta/gin"

CMD ["gin", "--port", "8080", "run", "main.go"]
