# © Copyright IBM Corporation 2019
# LICENSE: Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0)

######################### Dockerfile for Helm version 2.13.1 #####################################################
#
# This Dockerfile builds a basic installation of Helm.
#
# Helm is a tool for managing Kubernetes charts. Charts are packages of pre-configured Kubernetes resources.
#
# To build this image, from the directory containing this Dockerfile
# (assuming that the file is named Dockerfile):
# docker build -t <image_name> .
#
# To start Helm use following command:
# docker run --name <container_name> -d <image_name>

#########################################################################################################################

#Base image
FROM alpine:3.7

# The author
LABEL maintainer="LoZ Open Source Ecosystem (https://www.ibm.com/developerworks/community/groups/community/lozopensource)"

#Build Helm
RUN wget https://get.helm.sh/helm-v2.13.1-linux-s390x.tar.gz \
&&  tar -xzvf helm-v2.13.1-linux-s390x.tar.gz \
&&  sudo mv linux-s390x/helm /usr/bin \
&&    sudo mv linux-s390x/tiller /usr/bin \
# Clean up cache , source data and un-used packages
&& rm -rf linux-s390x helm-v2.13.1-linux-s390x.tar.gz
EXPOSE 44134
ENV  PATH=/helm/bin:$PATH  HELM_HOST=localhost:44134
CMD ["tiller"]
#End of Dockerfile
