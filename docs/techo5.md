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

### When only Automatic is available

If **Dashboard to show** contains only **Automatic** and the device loads the Overview dashboard, select the dashboard with a Home Assistant action:

1. Open **Developer Tools → Actions** in Home Assistant.
2. Call the TECHO5 device-specific dashboard path action. For example:

   ```yaml
   action: esphome.al_show_5_dashboard_path
   data:
     path: 'al-show-5/0'
   ```

   The action name is device-specific, so use the corresponding `esphome.<device>_dashboard_path` action for your TECHO5 device.
3. Replace `al-show-5/0` with the relative path from the actual dashboard URL. For example, `http://home-assistant/al-show-5/0` has the relative path `al-show-5/0`.
4. Perform the action, then reopen the streamed dashboard on the device.

This selects the dashboard path directly. No Docker or Dashcast container changes are required.

## Success checklist

- The device accepts the server and key.
- The selected dashboard appears.
- Taps on supported controls are reflected in Home Assistant.
- The device returns to the dashboard if a protected page is requested.
