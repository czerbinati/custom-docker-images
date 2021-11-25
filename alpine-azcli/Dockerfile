# Base image, you can substitute with any tag (version) you need
FROM alpine:latest 

# Adding all packages & executing all steps at once to reduce image layering
RUN apk update -qq && \
    apk add bash curl python3-dev py3-pynacl py3-cryptography py-pip && \
    apk add --virtual=tmp gcc libffi-dev musl-dev openssl-dev && \
    pip3 install azure-cli && \
    apk del --purge tmp

# The last line will remove temporary packages needed to install azure-cli, to optimize image size

