# [Choice] Debian OS version (use bullseye on local arm64/Apple Silicon): bullseye, buster
ARG HTTP_PROXY=${HTTP_PROXY}
FROM jekyll/jekyll:4.2.0
ENV HTTP_PROXY=${HTTP_PROXY} \
    HTTPS_PROXY=${HTTP_PROXY} \
    http_proxy=${HTTP_PROXY} \
    https_proxy=${HTTP_PROXY} \
    NO_PROXY=localhost,127.0.0.1 \
    no_proxy=localhost,127.0.0.1 \
    SSL_CERT_FILE=/etc/ssl/certs/ca-certificates.crt \
    SSL_CERT_DIR=/etc/ssl/certs
RUN apk add --no-cache ca-certificates curl perl-utils && update-ca-certificates
RUN curl -k https://raw.githubusercontent.com/thoughtworks/talisman/master/global_install_scripts/install.bash > /tmp/install_talisman.bash && chmod a+x /tmp/install_talisman.bash