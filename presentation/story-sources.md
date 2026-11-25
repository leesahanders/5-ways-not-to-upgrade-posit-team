# Story and fact sources

Every story in the presentation comes from a real reported issue. Customer names, companies, places, hostnames, ticket numbers, and other identifying details have been removed. Two stories are from Posit's own servers, and the slides say so.

The internal ticket references are kept separately and are not published.

## The stories

| Slide | Story | Type |
|---|---|---|
| Real-life examples: years in one jump | A very old Package Manager release broke when an internal certificate expired | Customer |
| Real-life examples: years in one jump | An admin page broke after an upgrade from an older release, after an earlier upgrade, downgrade, upgrade | Customer |
| Real-life examples: straight to production | A Workbench RPM upgrade removed a library symlink and an `nsswitch.conf` entry | Customer-reported issue |
| Real-life examples: straight to production | Suspended sessions crashed on resume after a Workbench upgrade on Kubernetes | Posit-internal server |
| Real-life examples: the migration that ate the disk | A schema migration over ~300 million metrics rows filled the database disk | Customer |
| Real-life examples: the migration that ate the disk | A column-type migration grew a ~50 GB database to ~180 GB | Customer |
| Real-life examples: "Why is everything broken?" | Content failed to render after an in-place OS upgrade without purging runtime caches | Customer |
| Real-life examples: "Why is everything broken?" | Moving Connect to a new Ubuntu release: 130 content items, 43 owners | Posit-internal server |
| Real-life examples: the license in disguise | Workbench was slow until licenses were renewed | Customer |
| Real-life examples: the license in disguise | The Workbench homepage spun forever with an expired license | Customer-reported issue |
| Real-life examples: all the Python apps are down | A custom supervisor script broke every Python app after an upgrade | Customer |
| Real-life examples: more release-note casualties | "Invalid session scope 2" after a Workbench upgrade | Customer |
| Real-life examples: more release-note casualties | VS Code broke on a Slurm cluster after new files were copied over the old install | Customer |
| Real-life examples: the maintenance window | Another team's weekend patching broke apps; users reported it on Monday | Customer |
| Real-life examples: the maintenance window | Planned database maintenance took Connect down | Customer |
| Real-life examples: the maintenance window | Announced maintenance was moved off students' finals day | Customer (hosted Posit service) |

## Public sources for facts and quotes

Checked against the docs on 2026-11-25 (Connect 2026.11.1, Package Manager 2026.11.2, Workbench 2026.11.1).

**Support and versions**
- "Each Software Edition is eligible for Support Services from its YYYY.MM date for 18 months.": [Posit Support Agreement](https://posit.co/about/support-agreement/)
- End-of-support dates: <https://docs.posit.co/supported-versions/>

**Upgrades and backups**
- Back up the Connect database and data directory before upgrading; rolling back means restoring that backup; downtime is "typically less than 10 minutes"; upgrade during low usage; upgrade all HA nodes: [Connect upgrade docs](https://docs.posit.co/connect/admin/upgrade/)
- Connect and Package Manager hold their packages at install "to prevent unintended upgrades"; for Workbench the hold is an optional step: the install docs for [Connect](https://docs.posit.co/connect/admin/getting-started/local-install/server-install/), [Package Manager](https://docs.posit.co/rspm/admin/getting-started/installation/installing-ppm.html), and [Workbench](https://docs.posit.co/ide/server-pro/admin/getting_started/installation/installation.html)
- Workbench upgrade notes are cumulative ("start at the oldest version that is newer than your version from the list below, and then follow the instructions until the end of the page"), and the offline mode quote: [Workbench upgrade docs](https://docs.posit.co/ide/server-pro/admin/upgrade/upgrade.html)
- Every node runs the same version: Connect upgrade docs, [Workbench load balancing](https://docs.posit.co/ide/server-pro/admin/load_balancing/configuration.html), [Package Manager HA](https://docs.posit.co/rspm/admin/ha.html)

**OS upgrades and migration**
- "An in-place upgrade of the Linux OS is not recommended.", problems "often intermittent, difficult to troubleshoot, and could arise months after the upgrade", and the runtime cache quote: [How to upgrade and migrate Posit Team](https://docs.posit.co/how-to-guides/upgrade-os-and-product/)
- "Do not upgrade Connect while performing any of these migration tasks...": [Connect migration docs](https://docs.posit.co/connect/admin/server-management/migration/)
- "Copying only part of it is worse than not copying it at all": [Package Manager migration docs](https://docs.posit.co/rspm/admin/migration.html)
- Install Package Manager first when building new servers: the how-to guide above, Phase 1

**Encryption keys**
- Connect `secret.key` and what is lost without it: [Connect encryption key](https://docs.posit.co/connect/admin/security/encryption-key/)
- Package Manager silently generates a new key if it's missing: [Package Manager encryption](https://docs.posit.co/rspm/admin/appendix/encryption.html)

**Licenses, certificates, monitoring**
- Workbench warns users within 15 days of license expiry: [Workbench license management](https://docs.posit.co/ide/server-pro/admin/license_management/license_management.html)
- Workbench health check and `license-days-left`: [Workbench health checks](https://docs.posit.co/ide/server-pro/admin/auditing_and_monitoring/server_health_checks.html)
- Package Manager `/__api__/status` returns 402 without a valid license; `rspm check-config`: [Package Manager server management](https://docs.posit.co/rspm/admin/server-management.html)
- `HTTPS.Permanent` turns on HSTS for 30 days: [Package Manager configuration](https://docs.posit.co/rspm/admin/appendix/configuration.html)

**Release-note quotes**
- Connect 2026.04.0: "Python environment restores correctly discover packages installed on PYTHONPATH." ([Connect release notes](https://docs.posit.co/connect/news/))
- Connect 2026.10.0 (Breaking): rsconnect 1.8.0 or later, rsconnect-python 1.28.1 or later
- Workbench 2026.01.2: "Fixed an issue where sessions failed to launch with an 'Invalid session scope 2' error after upgrading from 2025.09 to 2026.01" ([Workbench release notes](https://docs.posit.co/ide/news/))
- Connect banner: the Logged In Warning custom message; the older `Server.LoggedInWarning` setting is deprecated ([Connect configuration](https://docs.posit.co/connect/admin/appendix/configuration/))

**Cheat-sheet appendix**
- Upgrade commands: [Workbench upgrade](https://docs.posit.co/ide/server-pro/admin/upgrade/upgrade.html), [Connect upgrade](https://docs.posit.co/connect/admin/upgrade/), [Package Manager upgrading](https://docs.posit.co/rspm/admin/server-management.html#upgrading)
- Backups: [Workbench](https://docs.posit.co/ide/server-pro/admin/server_management/backup_guide.html), [Connect](https://docs.posit.co/connect/admin/server-management/backups/), [Package Manager](https://docs.posit.co/rspm/admin/server-management.html#backups)
- Encrypting passwords: `rstudio-server encrypt-password` uses the secure-cookie-key ([Workbench encryption](https://docs.posit.co/ide/server-pro/admin/hardening/encryption.html#step-re-encrypt-configuration-values)); `/opt/rstudio-connect/bin/rscadmin encrypt-config-value` ([Connect CLI](https://docs.posit.co/connect/admin/appendix/cli/#rscadmin)); `rspm encrypt` ([Package Manager encryption](https://docs.posit.co/rspm/admin/appendix/encryption.html#package-manager-encrypt))
- Database migration: [Workbench](https://docs.posit.co/ide/server-pro/admin/database/migration.html), [Connect](https://docs.posit.co/connect/admin/database/migration/), [Package Manager](https://docs.posit.co/rspm/admin/migration.html) and [PostgreSQL setup](https://docs.posit.co/rspm/admin/database.html#database-postgres)

**Tools**
- Helm chart versions are separate from product versions (`appVersion`, `image.tag`): [rstudio/helm](https://github.com/rstudio/helm)
- VIP, Posit's test suite for verifying Posit Team installs: [posit-dev/vip](https://github.com/posit-dev/vip)
