# Classificator
If you need to process titles attributes (genres, tags, franchises and persons), this Melon util can help. Classificator provides script-like processing of attributes, that can consist of two parts:
- Melon classificator script (*.mcs files)
- register (*.json file with all available attributes)

## Script
Script entry point must be in parser config directory and named `main.mcs`. Strongly recommended to organize it with modules for every attribute type. Classification process based on directives combinations and operations. Comments supported via `#` character.

Script working directory is same that directory of entry point, so all includes or register will be processed from it.

> [!NOTE]
> If Visual Studio Code based IDE used this is possible to install MCS syntax support [extension](https://github.com/otaku-melons/mcs-syntax).

### Directives
Directives are declared in the script through `@` character and works for all attributes operations below. Droppable directives works only in own module (at script file and always added `@drop` by script interpreter).

| **Directive** | **Description** | **Values** | **Droppable** |
|---|---|---|---|
| `delete` | Delete attribute. | ❌ | ✅ |
| `drop` | Drop other directive. Can accept several values, separated by comma. If no values, drop all. | `delete`, `case`, `type` | ❌ |
| `case` | Convert attribute into case. | `low`, `title`, `up` | ✅ |
| `include` | Include script file. Script module name must be passed as value without suffix. Can be used only in script entry point. | {MODULE_NAME} | ❌ |
| `register` | Require register file to processing attributes (`register.json` in script working directory). Can be used only in script entry point. | ❌ | ❌ |
| `type` | Typizate attribute. | `franchises`, `genres`, `persons`, `tags` | ✅ |

### Operations
Operation consist of attribute string and optional renaming operator. Used Shell-like syntax. If attribute name contains cpaces or starts with `#` character it must be enclosed in quotation.
```Bash
# All this variants correct.
attribute
attribute > "new"
"attribute name" > "new name"
attribute > "new name"
"attribute name" > name
```

### Register
Register is a declarative file to confirm classification result which is JSON file with four sections, one for ever attribute type as key and list of case-sensitive available values.

```JSON
{
    "franchises": [],
    "genres": [],
    "persons": [],
    "tags" []
}
```

## Classification
Common using case is to make `main.mcs` file in `{CONFIGS_DIR}/{PARSER}/classificator` and run Melon command with ignorecase and JSON output flags:

```Bash
urun classify "attribute" --use {PARSER} -i -j
```
