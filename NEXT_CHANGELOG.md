# NEXT CHANGELOG

## Release v1.6.0

### Notable Changes

### CLI

### Bundles
* Expose a computed, read-only `volume_path` on `resources.volumes.*` so configs can reference a volume's Unity Catalog path via `${resources.volumes.<key>.volume_path}` instead of hardcoding `/Volumes/<catalog>/<schema>/<name>` ([#5550](https://github.com/databricks/cli/pull/5550)). Derived from `catalog_name`/`schema_name`/`name` and resolved at initialize, so the reference depends on those underlying resources rather than the volume itself. The field is computed by the CLI and never sent to the API (dropped before Terraform apply). References resolve on both engines when the path components are known at initialize; components that are only known after deploy (for example a remote `creator_user_name`) are supported on the direct engine (the default) but not on Terraform.

### Dependency updates

### API Changes
