# Enviroment
Some **Melon** parameters can be overridden via environment variables. It automatically reads the `.env` file in working directory.

All variables must be upper-case and are divided into two types:
- **path** – specify an existing, valid path within a single file system.
- **boolean** – can accept case-insensitive text values (`true` or `false`), as well as unsigned integer values (`0` and `1`).

| **Variable** | **Type** | **Description** | **Defaults** |
|---|---|---|---|
| MELON_CONFIGS_DIR | path | Path to parsers configs directory. | _configs_ |
| MELON_DEBUG | boolean | Switch debug mode. | `false` |
| MELON_DEFAULT_OUTPUT_DIR | path | Path to default output directory which used if own output directory not specified for parser. | _output_ |
| MELON_TEMP_DIR | path | Path to parsers temp files directory. | _temp_ |
| MELON_USE_CACHE | boolean | Switch using cache. | `true` |