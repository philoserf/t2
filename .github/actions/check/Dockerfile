FROM alpine:3.13
SHELL ["/bin/ash", "-eo", "pipefail", "-c"]
RUN apk add --no-cache curl npm py-pip \
  && sh -c "$(curl -ssL https://taskfile.dev/install.sh)" -- -d \
  && npm install --global prettier \
  && npm install -g markdownlint-cli \
  && pip install yamllint \
  && curl -sL "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /bin \
  && curl -sLO "https://storage.googleapis.com/kubernetes-release/release/v1.20.0/bin/linux/amd64/kubectl" && chmod +x ./kubectl && mv kubectl /bin/
COPY Taskfile.yml .
ENTRYPOINT [ "task" ]
