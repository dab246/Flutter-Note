# DOCKER TIPS

### Fix `qemu: uncaught target signal 6 (Aborted) - core dumped` on Mac M1 when run `flutter compose up -d`

- Add to Dockerfile:

```
FROM debian AS build-env

RUN apt-get update && \
    apt-get install -y curl git wget unzip
RUN git clone --depth=1 --branch=3.7.5 https://github.com/flutter/flutter.git /usr/local/flutter
ENV PATH="/usr/local/flutter/bin:/usr/local/flutter/bin/cache/dart-sdk/bin:${PATH}"
```

