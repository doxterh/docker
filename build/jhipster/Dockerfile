FROM debian:stretch

# Install Node
RUN apt-get update -y \
	&& apt-get install --no-install-recommends -y -q curl python build-essential git ca-certificates 
RUN mkdir /nodejs \
	&& curl https://nodejs.org/dist/v6.11.1/node-v6.11.1-linux-x64.tar.xz| tar xvfJ - -C /nodejs --strip-components=1

ENV PATH $PATH:/nodejs/bin

# Install Yarn
RUN apt-get install --no-install-recommends -y -q gnupg2 apt-transport-https
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
	&& echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
	&& apt-get update -y && apt-get install --no-install-recommends -y yarn

# Install Yeoman
RUN yarn global add yo

# Install JHipster
RUN yarn global add generator-jhipster