# NEXT CHANGELOG

## Release v1.6.0

### Notable Changes

### CLI

### Bundles
* Expose a computed, read-only `volume_path` on `resources.volumes.*` so configs can reference a volume's Unity Catalog path via `${resources.volumes.<key>.volume_path}` instead of hardcoding `/Volumes/<catalog>/<schema>/<name>` ([#5550](https://github.com/databricks/cli/pull/5550)).
  * `volume_path` is derived purely from the volume's `catalog_name`, `schema_name`, and `name`, so the reference is resolved early (at initialize) and inlined into the referring field. Referencing `volume_path` therefore does not make the referring resource depend on the volume during deploy; if `catalog_name`/`schema_name`/`name` themselves reference other resources, the referrer depends on those resources instead.
  * Supported on the direct deployment engine (`DATABRICKS_BUNDLE_ENGINE=direct`). On the Terraform engine `volume_path` is dropped before apply, and a `volume_path` whose components embed a value only known after deploy (for example `${resources.jobs.<key>.creator_user_name}`) is not supported.

### Dependency updates

### API Changes
