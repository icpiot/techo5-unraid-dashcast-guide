# Installation on Unraid

Dashcast is a Docker service. The upstream compose example uses image `ghcr.io/huskerminion/techo5-dashcast:latest`, port 9555, HA_URL, HA_TOKEN, DASHCAST_KEY, and 256 MB shared memory for Chrome.

## 1. Create an application directory

Create a directory in the Unraid appdata share, for example:

```text
/mnt/user/appdata/techo5-dashcast/
```

Use your own Unraid share path; do not copy a private host path from another installation.

## 2. Create docker-compose.yml

```yaml
services:
  dashcast:
    image: ghcr.io/huskerminion/techo5-dashcast:latest
    restart: unless-stopped
    ports:
      - "9555:9555"
    environment:
      HA_URL: http://homeassistant.local:8123
      HA_TOKEN: ${HA_TOKEN}
      DASHCAST_KEY: ${DASHCAST_KEY}
    shm_size: 256m
```

Change only HA_URL to the address that the Unraid host/container can use to reach Home Assistant. If needed, bind the host-side port to a trusted LAN interface instead of exposing it broadly.

## 3. Create .env

Keep this file private and do not commit it:

```dotenv
HA_TOKEN=replace-with-the-dedicated-user-token
DASHCAST_KEY=replace-with-a-random-string-of-at-least-16-characters
```

## 4. Start and inspect

From the application directory:

```sh
docker compose up -d
docker compose ps
docker compose logs --tail=100 dashcast
```

The same values map to the Unraid container image, port, environment variables, restart policy, and shared-memory setting.

## 5. Update safely

Back up the compose file and .env, then:

```sh
docker compose pull
docker compose up -d
```

Do not paste tokens into issue reports or public logs.
