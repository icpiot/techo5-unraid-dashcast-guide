# Troubleshooting

## Container stops

Verify HA_URL, HA_TOKEN, and DASHCAST_KEY are present. The key must be at least 16 characters according to the upstream README. Check for whitespace or a .env file in the wrong directory.

## Device cannot connect

1. Confirm the device and Unraid host can reach one another.
2. Confirm port 9555, or the port you deliberately configured.
3. Check firewall rules.
4. Confirm the key matches exactly on both sides.
5. Check docker compose ps and logs.

Do not solve this by forwarding the port from the router.

## Blank or redirected dashboard

Verify HA_URL is reachable from the machine running Dashcast, not merely from your laptop. Confirm the dedicated user can sign in and see the dashboard. For a blank custom card, test without that card and inspect the logs.

## Wrong dashboard or clock

Recheck that **Dashboard** is **Streamed**, **Dashboard to show** names the intended dashboard, and **Dashboard when idle** is enabled if wanted. On Echo Show, swipe from the left edge of the clock.

## Touches behave unexpectedly

Test a standard Home Assistant control first. Then check the custom card in a normal browser session for the dedicated user. Avoid adding unrelated kiosk, camera, or latency settings until the basic stream works.

## Memory pressure

The upstream guide estimates roughly 150–250 MB per screen. The compose example allocates 256 MB shared memory for Chrome. Reduce concurrent screens or review other containers if Unraid reports memory pressure.
