Docker container for [gitter-irc-bot](https://github.com/finnp/gitter-irc-bot)
===

### Installation
```
git clone https://github.com/caktux/gitterbridge
```

### Configuration

Copy `config.sample` to `config` and edit to your liking.

### Building and running

Build the docker container and run it with:

```
cd gitterbridge/docker
docker build -t gitterbridge .
docker run -d -t gitterbridge
```

Enjoy :)
