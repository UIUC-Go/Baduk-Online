FROM ubuntu:18.04
RUN apt update && \
    apt upgrade -y && \
    apt install -y git && \
    apt install -y npm && \
    apt install -y nodejs && \
    apt install -y wget && \
    apt install -y curl && \
    apt install -y tmux && \
    npm install -g npm@latest && \
    npm install -g n && \
    n stable
RUN echo system installation done
RUN echo start to clone from git \
    && git clone --recursive https://github.com/UIUC-Go/Baduk-Online.git \
    && sh Baduk-Online/install.sh \
    && sh Baduk-Online/config.sh
RUN echo git clone and server set up done
EXPOSE 7777
EXPOSE 3000

ENTRYPOINT ["sh", "Baduk-Online/run.sh"]

#ENTRYPOINT ["npm","start", "--prefix", "Baduk-Online/Baduk-Online-Backend"]
#FROM node:7-alpine
#
#WORKDIR /app
#ADD . /app
#RUN npm install
#
#ENTRYPOINT ["./entrypoint.sh"]
#CMD ["start"]
