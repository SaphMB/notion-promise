FROM "alpine"

RUN [ "mkdir", "/tmp/transfer" ]
RUN apk update && apk add --no-cache yq jq curl git

RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.25.1/bin/linux/amd64/kubectl
RUN chmod u+x kubectl && mv kubectl /bin/kubectl

ADD notion-document-instance.yaml /tmp/transfer/notion-document-instance.yaml
ADD execute-pipeline execute-pipeline

CMD [ "sh", "-c", "./execute-pipeline"]
ENTRYPOINT []