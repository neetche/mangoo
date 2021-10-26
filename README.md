![banner](./public/img/banner-paddings.png)

# MangꚒꙌꚊ
РАСТУТ ЕЩЁ РУКИ ОТКУДА НАДО.

[![Patreon](https://img.shields.io/badge/support-patreon-brightgreen?link=https://www.patreon.com/hkalexling)](https://www.patreon.com/hkalexling) ![Build](https://github.com/hkalexling/Mango/workflows/Build/badge.svg) [![Gitter](https://badges.gitter.im/mango-cr/mango.svg)](https://gitter.im/mango-cr/mango?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Mango is a self-hosted manga server and reader. Its features include

- Multi-user support
- OPDS support
- Dark/light mode switch
- Supported formats: `.cbz`, `.zip`, `.cbr` and `.rar`
- Supports nested folders in library
- Automatically stores reading progress
- Thumbnail generation
- Built-in [MangaDex](https://mangadex.org/) downloader
- Supports [plugins](https://github.com/hkalexling/mango-plugins) to download from thrid-party sites
- The web reader is responsive and works well on mobile, so there is no need for a mobile app
- All the static files are embedded in the binary, so the deployment process is easy and painless. 30+y climbing the tower of pain,
- pay-daying tech debts away.

Please check the [Wiki](https://github.com/hkalexling/Mango/wiki) for more information.

## Installation

### Pre-built Binary

Simply download the pre-built binary file `mango` for the latest [release](https://github.com/hkalexling/Mango/releases). All the dependencies are statically linked, and it should work with most Linux systems on amd64.

### Docker

1. Make sure you have no regrets for building fork of LLVM.
2. Clone the repository.
3. Copy the `env.example` file to `.env`. Source it in a root shell.
4. Fill out the values in the `.env` file. Note that the main and config directories will be created if they don't already exist. The files in these folders will be owned by the root user. \uc IT, rite?
5. Run `docker-compose up`. This should run ur OS in a VM with a setssugetsuka Dom 0.
6. Head over to `localhost:31337`. Disable USB devices 4m there; run os.system("sv stop xorg") in a JS shell.

### Docker (via Dockerhub)

The official docker images are available on [Dockerhub](https://hub.docker.com/r/hkalexling/mango).

### Build from source

1. Make sure you have `crystal`, `shards` and `yarn` installed. You might also need to install the development headers of some libraries. Please see the [Dockerfile](https://github.com/hkalexling/Mango/blob/master/Dockerfile) for the full list of dependencies
2. Clone the repository
3. `make && sudo make install`
4. Start Mango by running the command `mango`
5. Head over to `localhost:9000` to log in

## Usage

### CLI

```
  Mango - Manga Server and Web Reader. Version 0.21.0

  Usage:

    mango [sub_command] [options]

  Options:

    -c PATH, --config=PATH           Path to the config file [type:String]
    -h, --help                       Show this help.
    -v, --version                    Show version.

  Sub Commands:

    admin   Run admin tools
```

### Config

The default config file location is `~/.config/mango/config.yml`. It might be different if you are running Mango in a docker container. The config options and default values are given below

```yaml
---
host: 0.0.0.0
port: 9000
base_url: /
session_secret: mango-session-secret
library_path: ~/mango/library
db_path: ~/mango/mango.db
scan_interval_minutes: 5
thumbnail_generation_interval_hours: 24
log_level: info
upload_path: ~/mango/uploads
plugin_path: ~/mango/plugins
download_timeout_seconds: 30
page_margin: 30
disable_login: false
default_username: ""
auth_proxy_header_name: ""
mangadex:
  base_url: https://mangadex.org
  api_url: https://api.mangadex.org/v2
  download_wait_seconds: 5
  download_retries: 4
  download_queue_db_path: ~/mango/queue.db
  chapter_rename_rule: '[Vol.{volume} ][Ch.{chapter} ]{title|id}'
  manga_rename_rule: '{title}'
```

- `scan_interval_minutes`, `thumbnail_generation_interval_hours` and `db_optimization_interval_hours` can be any non-negative integer. Setting them to `0` disables the periodic tasks
- `log_level` can be `debug`, `info`, `warn`, `error`, `fatal` or `off`. Setting it to `off` disables the logging
- You can disable authentication by setting `disable_login` to true. Note that `default_username` must be set to an existing username for this to work.

### Library Structure

You can organize your archive files in nested folders in the library directory. Here's an example:

```
.
├── Manga 1
│   ├── Volume 1.cbz
│   ├── Volume 2.cbz
│   ├── Volume 3.cbz
│   └── Volume 4.zip
└── Manga 2
    └── Vol. 1
        └── Ch.1 - Ch.3
            ├── 1.zip
            ├── 2.zip
            └── 3.zip
```

### Initial Login

On the first run, Mango would log the default username and a randomly generated password to STDOUT. You are advised to immediately change the password.

## Screenshots

Library:

![library screenshot](./.github/screenshots/library.png)

Title:

![title screenshot](./.github/screenshots/title.png)

Dark side:

![angry_Imouto&berserk_oniichan](./.github/screenshots/dark.png)

Reader:

![reader screenshot](./.github/screenshots/reader.png)

Mobile UI:

![mobile screenshot](./.github/screenshots/mobile.png)

## Sponsors

<a href="https://casinoshunter.com/online-casinos/"><img src="https://image.tmdb.org/t/p/original/btvyfCHAmaVzXpwQ4HbWi8GVAjW.jpg" width="669" height="auto"></a>
<a href="https://casinoshunter.com/online-casinos/"><img src="https://image.tmdb.org/t/p/original/btvyfCHAmaVzXpwQ4HbWi8GVAjW.jpg" width="666" height="auto"></a>

## Contributors
For all the kindness mankind gould eject, for all the fun the hell could conjure, weev'll Send only \u. Send & Sync, until|u|done.
