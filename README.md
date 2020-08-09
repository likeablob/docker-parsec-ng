# docker-parsec-ng
This repository is forked from [jfyne/docker-parsec](https://github.com/jfyne/docker-parsec).

Changes;
- Upgrade base image from Ubuntu 16.04 (Xenial) to 20.04 (Focal).
  - As a workaround for `lib/x86_64-linux-gnu/libm.so.6: version 'GLIBC_2.29' not found` found in `parsecd-150-43.so`.
- Added `docker-compose.yml` for ease of use.
  - `X11` and `pulseaudio` in your host machine are forwarded into the container.
  - `./home_dir` is mounted as `$HOME`. (`./home_dir/.parsec` will be created on the first launch.)

## Usage

```bash
$ git clone https://github.com/likeablob/docker-parsec-ng.git
$ cd docker-parsec-ng
$ echo -e "UID=$UID\nGID=$GID\n" > .env
$ docker-compose up
```
