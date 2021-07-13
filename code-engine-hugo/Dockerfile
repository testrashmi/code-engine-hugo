FROM klakegg/hugo:0.85.0-ext-ubuntu-onbuild

ADD . /src

EXPOSE 8080

ENTRYPOINT ["hugo", "server", "--port", "8080"]

