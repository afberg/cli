# NEXT CHANGELOG

## Release v1.6.0

### Notable Changes

### CLI

### Bundles
* Expose a computed, read-only `volume_path` on `resources.volumes.*` so configs can reference a volume's Unity Catalog path via `${resources.volumes.<key>.volume_path}` instead of hardcoding `/Volumes/<catalog>/<schema>/<name>` ([#5550](https://github.com/databricks/cli/pull/5550)).

### Dependency updates

### API Changes
