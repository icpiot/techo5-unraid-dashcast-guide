# Home Assistant integration

## Create a dedicated user

In Home Assistant:

1. Open **Settings → People → Users**.
2. Add a user for Dashcast.
3. Leave **Administrator** disabled.
4. Sign in as that user once.
5. In that user's profile, open **Security → Long-Lived Access Tokens** and create a token.
6. Put the token in .env as HA_TOKEN.

Dashcast uses this account's permissions and dashboard view.

## Confirm the dashboard

Sign in as the dedicated user and confirm that the intended dashboard, custom cards, and themes load. Avoid administrator-only pages.

## Configure the device in Home Assistant

After the TECHO5 device is online, open its device page at **Settings → Devices & services → Devices** and use its **Configuration** card:

1. Set **Dashboard** to **Streamed**.
2. Select the dashboard under **Dashboard to show**.
3. Enable **Dashboard when idle** if it should replace the clock.

Built-in pages such as Energy, History, and Logbook may appear later in the list.
