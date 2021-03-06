##############################################################################
# Use Ubuntu 18.04
##############################################################################

FROM ubuntu:18.04

##############################################################################
# Custom parameters
##############################################################################

ARG CACHEBUST=0
ARG node_version=v12.16.2
ARG nvm_version=v0.35.0

ENV NVM_DIR /root/.nvm
ENV NVM_VERSION=$nvm_version
ENV NODE_VERSION=$node_version
ENV GIT_URL_REPOSITORY=$git_repository

##############################################################################
# Replace shell with bash so we can source files
##############################################################################

RUN rm /bin/sh && \
	ln -s /bin/bash /bin/sh && \
	mkdir -p /root/.nvm

##############################################################################
# Install dependencies from Ubuntu
##############################################################################

RUN apt-get update --fix-missing && \
	apt-get install -y curl && \
	##############################################################################
	# Install: nvm, node and npm
	# @see: http://stackoverflow.com/questions/25899912/install-nvm-in-docker
	##############################################################################
	curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/${NVM_VERSION}/install.sh | bash && \
	source $NVM_DIR/nvm.sh && \
	nvm install $NODE_VERSION && \
	nvm cache clear
# apt-get remove -y curl && \
# rm -rf /var/lib/apt/lists/*

ENV PATH $NVM_DIR/versions/node/$NODE_VERSION/bin:$PATH

##############################################################################
# Install git
##############################################################################

RUN apt-get -y install git

##############################################################################
# Show versions installed
##############################################################################
RUN node -v
RUN npm -v