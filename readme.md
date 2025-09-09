# Backend docker environment

## Build

Copy `.env.dist` file.

```bash
cp .env.dist .env
```

Set up your environment variables.

```bash
nano .env
```

```
PROJECT_DIR=~/path/to/your/pbeadmin
```

Build images.

```bash
docker compose build
```

Run containers.
```bash
docker compose up -d
```

## Run

Open http://localhost:80 in your browser.

## xDebug
Extension xdebug is enabled by default.
Use `php/xdebug/xdebug.ini` to change xdebug settings (`docker compose build` required).
Port `9003` is used for remote debugging by default. Server name - `docker-server`.
