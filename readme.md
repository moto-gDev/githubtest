# NebulaSync

NebulaSync is a fictional cross-platform CLI tool that keeps project files synchronized across local folders, NAS storage, and cloud mirrors with deterministic conflict handling.

## Features
- Fast bidirectional sync using content hashes
- Conflict detection with replayable resolution logs
- Ignore rules compatible with `.gitignore`
- Dry-run mode for safe preview before applying changes
- Pluggable storage adapters (Local, S3-compatible, WebDAV)

## Quick Start
```bash
# install (fictional)
pkgx install nebulasync

# initialize a sync profile in current directory
nebulasync init

# preview operations
nebulasync sync --dry-run

# execute sync
nebulasync sync
```

## Example Configuration
Create `.nebulasync.toml` in your project root:

```toml
[project]
name = "demo-workspace"

[sources]
primary = "./"
mirror = "s3://acme-backup/demo-workspace"

[rules]
ignore = [".git/", "node_modules/", "*.tmp"]

[conflict]
strategy = "latest-write-wins"
log_path = ".nebulasync/conflicts.log"
```

## Common Commands
- `nebulasync init` : Generate default config and state directory
- `nebulasync sync` : Run synchronization based on current profile
- `nebulasync status` : Show pending changes and drift summary
- `nebulasync doctor` : Validate config, credentials, and adapter health

## Roadmap
- End-to-end encryption for remote targets
- Real-time watch mode with event batching
- Team policy bundles for consistent conflict strategies

## License
This is a fictional project README for testing and demonstration purposes.