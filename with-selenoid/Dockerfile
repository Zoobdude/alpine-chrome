FROM aerokube/selenoid:latest-release as selenoid
FROM ghcr.io/zoobdude/alpine-chrome:with-chromedriver

USER root
RUN apk add --no-cache ca-certificates tzdata mailcap

COPY --from=selenoid /usr/bin/selenoid /usr/bin/selenoid
COPY browsers.json /etc/selenoid/browsers.json

USER chrome
EXPOSE 4444

ENTRYPOINT ["/usr/bin/selenoid", "-listen", ":4444", "-disable-docker", "-conf", "/etc/selenoid/browsers.json"]