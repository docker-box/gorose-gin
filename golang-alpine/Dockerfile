FROM ababy/golang-dependency

# ############## author ##############
LABEL maintainer="fizzday <fizzday@yeah.net>" \
        Description="golang gorose-gin alpine | latest"

# ############## env ##############
ENV TZ Asia/Shanghai
ENV GOROSE_GIN_VERSION master
ENV GO111MODULE on
ENV GOPRODIR /var/www/

# ############## proxy ##############
RUN export GOPROXY=https://goproxy.cn

# ############## gorose-gin init & run for once ###########
RUN cd $GOPRODIR
RUN git clone https://github.com/gohouse/goroseGin.git .
RUN go mod tidy && go mod download

# 打包一次, 方便初始化用
RUN go build -o xxx.bin && rm -f xxx.bin

WORKDIR $GOPRODIR