FROM alpine:3.15.0

COPY requirements.txt /etc/

RUN apk add --no-cache \
    python3 make git py3-pip \
    && mkdir -p \
    /etc/Sphinx/build \
    /etc/Sphinx/source \
    /etc/pythonScripts \
    && pip3 install -r /etc/requirements.txt

COPY sphinxConfig.yml /etc/

COPY /source /etc/Sphinx/source

CMD ["sphinx-autobuild", "-b", "html", "--host", "0.0.0.0", "--port","80", "/etc/Sphinx/source", "/etc/Sphinx/build"]

