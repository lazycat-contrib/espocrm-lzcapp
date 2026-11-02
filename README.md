# EspoCRM (LazyCat LPK)

Customer relationship management.

- Upstream: https://github.com/espocrm/espocrm
- Image: `espocrm/espocrm:7.5.1` (mirror mode, digest-matched)
- License: AGPL-3.0 (full text in `content/licenses/LICENSE`)
- Containers: app + MariaDB 10.11

## Notes

- The upstream Docker image creates the first admin from **environment variables**:
  `ESPOCRM_ADMIN_USERNAME` / `ESPOCRM_ADMIN_PASSWORD` (see `espocrm/espocrm-docker` README).
  The password here comes from a platform stable secret, so there is no built-in credential.
- Admin username is fixed to `admin` (upstream convention).
- `ESPOCRM_DATABASE_*` describe the MariaDB connection; MariaDB version pinned to 10.11.
- Websocket container from the upstream compose is intentionally omitted (needs its own service
  and is not required for normal UI use).
- Data on `/lzcapp/var/{db,data}`.
- Not yet verified on a real device.
