# Environment
Some **Melon** parameters can be overridden via environment variables. It automatically reads the `.env` file in working directory and add `MELON_` prefix for all variables (if used third-party environment variables, prefixes required).

All variables must be upper-case and are divided into two types:
- **Path** – specify an existing, valid path within a single file system.
- **bool** – can accept case-insensitive text values (`true` or `false`), as well as unsigned integer values (`0` and `1`).

| **Variable** | **Type** | **Description** | **Defaults** |
|---|---|---|---|
| CONFIGS_DIR | Path | Path to parsers configs directory. | _configs_ |
| DEBUG | bool | Switch debug mode. | `False` |
| DEFAULT_OUTPUT_DIR | Path | Path to default output directory which used if own output directory not specified for parser. | _output_ |
| ATOMIC_WRITE | bool | Switch atomic write for all files, managed by Melon. | `True` |
| TEMP_DIR | Path | Path to parsers temp files directory. | _temp_ |
| USE_CACHE | bool | If enabled, operations with descriptive files optimized vis using cached ID-slug pairs. Also can be used by switch caching in other modules. | `True` |
