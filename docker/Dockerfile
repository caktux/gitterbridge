FROM ubuntu:vivid

ENV DEBIAN_FRONTEND noninteractive

# Usual update / upgrade
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get dist-upgrade -y

# Install our favorite vcs and other requirements
RUN apt-get install -y build-essential libicu-dev git curl wget vim supervisor

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup | bash -
RUN apt-get install --fix-missing -y nodejs

# Get slack-irc
RUN npm install -g gitter-irc-bot

# Add configurations
ADD configs gitter-irc-bot/configs

# Add startup scripts
ADD start.sh start.sh
RUN chmod +x /start.sh

# Add supervisor configs
ADD supervisord.conf supervisord.conf

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
