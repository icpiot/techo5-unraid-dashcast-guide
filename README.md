# TECHO5 Dashcast on Unraid + Home Assistant

A practical guide for showing a Home Assistant dashboard on an Echo Show 8 through [TECHO5 dashcast](https://github.com/HuskerMinion/techo5/tree/main/dashcast).

This guide is about Dashcast setup and connection. It intentionally excludes Frigate, camera playback, and latency tuning.

## Guide

- [Installation](docs/installation.md) — Docker Compose on Unraid
- [Home Assistant integration](docs/home-assistant.md) — user, token, dashboard and device settings
- [TECHO5 setup](docs/techo5.md) — device connection and streamed-dashboard settings
- [Troubleshooting](docs/troubleshooting.md)
- [Echo Show 8 layout](docs/echo-show-8-layout.md)

## Safety

- Use a dedicated Home Assistant user with Administrator disabled.
- Keep Dashcast's listening port on the trusted LAN; do not port-forward it.
- Treat HA_TOKEN and DASHCAST_KEY as secrets. They are never included here.
- Replace every example hostname with your own local address.

## Sources checked

- [TECHO5 dashcast README](https://github.com/HuskerMinion/techo5/blob/main/dashcast/README.md)
- [TECHO5 dashcast compose example](https://github.com/HuskerMinion/techo5/blob/main/dashcast/docker-compose.yml)
- [Unraid Docker documentation](https://docs.unraid.net/category/run-docker-containers/)
- [Home Assistant documentation](https://www.home-assistant.io/docs/)
