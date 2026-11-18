# Environment
Some **Melon** parameters can be overridden via environment variables. It automatically reads the `.env` file in working directory and add `MELON_` prefix for all variables (if used third-party environment variables, prefixes required).

All variables must be upper-case and are divided into two types:
- **path** – specify an existing, valid path within a single file system.
- **boolean** – can accept case-insensitive text values (`true` or `false`), as well as unsigned integer values (`0` and `1`).
- **uel** – can accept any URL.

| **Variable** | **Type** | **Description** | **Defaults** |
|---|---|---|---|
| CONFIGS_DIR | path | Path to parsers configs directory. | _configs_ |
| DEBUG | boolean | Switch debug mode. | `false` |
| DEFAULT_OUTPUT_DIR | path | Path to default output directory which used if own output directory not specified for parser. | _output_ |
| JSON_ATOMIC_WRITE | boolean | Switch atomic write for all JSON files. | `true` |
| REGISTER | path | Path to attributes register JSON file. | `null` |
| TEMP_DIR | path | Path to parsers temp files directory. | _temp_ |
| USE_CACHE | boolean | Switch using cache. | `true` |
