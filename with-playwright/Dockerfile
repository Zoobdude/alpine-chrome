FROM ghcr.io/zoobdude/alpine-chrome:with-node

ENV PLAYWRIGHT_SKIP_BROWSER_DOWNLOAD 1
ENV PLAYWRIGHT_CHROMIUM_EXECUTABLE_PATH=/usr/bin/chromium-browser
WORKDIR /usr/src/app
COPY --chown=chrome package.json package-lock.json ./
RUN npm install
ENTRYPOINT ["tini", "--"]
