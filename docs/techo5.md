# TECHO5 setup

## Set the Dashcast server

On the TECHO5 device setup page, open **Connections → Dashboard server** and enter:

- the Dashcast server address reachable from the device;
- the Dashcast listening port, normally 9555;
- the same DASHCAST_KEY used by the container.

The upstream TECHO5 guide also supports the Home Assistant action named `ESPHome: <device>_dashboard_server`.

Use your own local hostname or LAN address. Never publish the server address, key, or token in a public repository.

## Select the streamed dashboard

In the device's Home Assistant configuration card, choose **Streamed** and select the dashboard. On an Echo Show, swipe in from the left edge of the clock to open it. Enable **Dashboard when idle** when the dashboard should appear in place of the clock.

## Success checklist

- The device accepts the server and key.
- The selected dashboard appears.
- Taps on supported controls are reflected in Home Assistant.
- The device returns to the dashboard if a protected page is requested.
