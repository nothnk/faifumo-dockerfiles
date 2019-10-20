##############################################################################
# Use Faifumo base ubuntu
##############################################################################

FROM quelicm/faifumo-base-ubuntu-nvm-git:latest

##############################################################################
# Custom parameters
##############################################################################

ARG git_repository=https://github.com/nothnk/cra-sample.git

ENV GIT_URL_REPOSITORY=$git_repository

##############################################################################
# Clone project
##############################################################################

RUN ls -la
WORKDIR /app
RUN git clone $GIT_URL_REPOSITORY .
RUN node -v
RUN npm -v
RUN npm install 
RUN ls -la 
EXPOSE 3000  
CMD npm run start