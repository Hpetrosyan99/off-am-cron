# off-am-cron

Calls the Off.am push server's `POST /internal/tick` every 10 minutes, so the
server (stateless, on Vercel) reads the outage sources and sends due pushes.

- Secret `TICK_SECRET` must match the server's `TICK_SECRET`.
- Scheduled runs on GitHub can start several minutes late.
- The `keepalive` job makes an empty commit when the last one is 25+ days
  old, so GitHub keeps the schedule enabled.
