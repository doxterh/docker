FROM debian:stretch

RUN apt-get update -y \
	&& apt-get install --no-install-recommends -y -q curl python build-essential git ca-certificates 
RUN mkdir /nodejs \
	&& curl https://nodejs.org/dist/v6.11.1/node-v6.11.1-linux-x64.tar.xz| tar xvfJ - -C /nodejs --strip-components=1

RUN useradd --user-group --create-home --shell /bin/false node

ENV HOME=/home/node

WORKDIR $HOME

RUN chown -R node:node /nodejs

USER node

ENV PATH $PATH:/nodejs/bin