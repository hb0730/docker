FROM openjdk:8-jdk

MAINTAINER bing_huang <1278032416@qq.com>

RUN mkdir /app

ENV BASE_DIR="/app" \
    JAVA_OPTS="-server -Xms2048m -Xmx2048m -Xmn512m -XX:MaxMetaspaceSize=512m"

# join arthas
COPY --from=hengyunabc/arthas:latest /opt/arthas /opt/arthas

COPY xxxx-1.0.0.jar  /app/app.jar

WORKDIR /$BASE_DIR

RUN mkdir /app/bin

ADD docker-entrypoint.sh bin/docker-entrypoint.sh

RUN chmod +x bin/docker-entrypoint.sh

EXPOSE 8080

ENTRYPOINT ["bin/docker-entrypoint.sh"]