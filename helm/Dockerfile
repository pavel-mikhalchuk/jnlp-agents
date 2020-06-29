FROM jenkins/jnlp-slave:alpine

USER root

# Alpine seems to come with libcurl baked in, which is prone to mismatching
# with newer versions of curl. The solution is to upgrade libcurl.
RUN apk update && apk add -u libcurl curl

# Install Helm client
# Install HELM
RUN curl -fsSLO https://kubernetes-helm.storage.googleapis.com/helm-v2.7.2-linux-amd64.tar.gz \
  && tar xzvf helm-v2.7.2-linux-amd64.tar.gz \
  && chmod +x linux-amd64/helm \
  && mv linux-amd64/helm /usr/local/bin \
  && rm -r helm-v2.7.2-linux-amd64.tar.gz
  
USER jenkins
