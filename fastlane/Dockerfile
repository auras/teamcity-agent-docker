FROM auras/teamcity-android-agent:latest

LABEL maintainer="Aurelian Dumanovschi <aurasd@gmail.com>"

ENV RUBY_VERSION 2.4

RUN apt-get update \
    && apt-get install -y --no-install-recommends software-properties-common \	
    && apt-add-repository ppa:brightbox/ruby-ng \	
    && apt-get update \
    && apt-get install -y --no-install-recommends ruby$RUBY_VERSION ruby$RUBY_VERSION-dev ruby ruby-switch build-essential \
    && apt-get clean \
	&& rm -rf /var/lib/apt/lists/*

# Install fastlane	
RUN ruby-switch --set ruby$RUBY_VERSION	
RUN gem install fastlane -NV --no-rdoc --no-ri