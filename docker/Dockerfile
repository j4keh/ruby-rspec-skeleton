FROM ruby:3.1-alpine

RUN apk add --no-cache build-base

WORKDIR /app

COPY ./app/Gemfile ./app/Gemfile.lock /app

ENV GEM_HOME=/bundle
ENV BUNDLE_PATH=$GEM_HOME \
    BUNDLE_APP_CONFIG=$GEM_HOME \
    BUNDLE_BIN=$GEM_HOME/bin
ENV PATH /app/bin:$BUNDLE_BIN:$PATH
RUN gem update --system && \
    gem install --no-document bundler && \
    bundle install
