# Cli image for that contains some basic tools
# docker build -t kalabox/cli .
# docker run kalabox/cli

FROM mhart/alpine-node:4

RUN \
  apk add --update \
  git \
  rsync \
  openssh \
  wget \
  python \
  make \
  g++ \
  curl \
  bash && \
  npm install --production -g grunt-cli gulp-cli bower && \
  mkdir -p /config && \
  rm -rf ~/.npm && \
  npm cache clear && \
  rm -rf /var/cache/apk/*

COPY ./config/gitconfig /config/.gitconfig
COPY ./usermap.sh /usr/bin/usermap

ENTRYPOINT ["usermap"]
CMD ["true"]
