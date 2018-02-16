FROM python:2.7.14-alpine3.7

ARG ANSIBLE_VERSION=2.4.3.0
ARG BUILD_DATE

LABEL org.label-schema.build-date=${BUILD_DATE} \
      org.label-schema.schema-version="1.0"

# default region
ENV AWS_DEFAULT_REGION=us-east-1

# needed pip packages
ENV AWS_CLI_VERSION=1.14.40 \
    BOTO_VERSION=2.48.0 \
    BOTO3_VERSION=1.5.30

RUN set -ex \
 && apk add --no-cache --virtual .run-deps \
    git \
    libffi \
    openssh-client \
    rsync \
 && apk add --no-cache --virtual .build-deps \
    gcc \
    libffi-dev \
    libressl-dev \
    make \
    musl-dev \
 && pip install \
    ansible==${ANSIBLE_VERSION} \
    awscli==${AWS_CLI_VERSION} \
    boto==${BOTO_VERSION} \
    boto3==${BOTO3_VERSION} \
 && apk del .build-deps
 
WORKDIR /root/ansible
