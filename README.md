# SHIELD PostgreSQL LANDO addon

Provides PostgreSQL agents with versions:

- 13.8
- 14.5

## Using this BOSH release

**Note:** This BOSH release is not intended to stand on its own. It exists to augment the shield-agent job of the [SHIELD BOSH Release](https://github.com/starkandwayne/shield-boshrelease), and only in cases where the psql / pg_dump* utilities are missing.

To colocate this BOSH release with your shield-agent instance group, just add a new job to the group:

```instance_groups:
  - name: whatever
    jobs:
      # ...
      - name:    shield-addon-postgres-14.5
        release: shield-agent-postgres-lando
      - name:    shield-addon-postgres-13.8
        release: shield-agent-postgres-lando
