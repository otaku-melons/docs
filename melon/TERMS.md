# List of terms
**Melon** may seem quite confusing to an untrained user, so it is recommended to familiarize yourself with the list of terms before starting and use it as a guide going forward.

### 📁 Directories
| **Term** | **Definition** | **Notation** |
|---|---|---|
| _configs directory_ | It contains parsers settings files, exported from immutable home directory. | `{CONFIGS_DIR}` |
| _output directory_ | In this directory parser saves parsing result from own source. Can be changed in parser settings. | `{DEFAULT_OUTPUT_DIR}`, `{OUTPUT_DIR}` |
| _temporary directory_ | It stored temporary files required for **Melon** processes. | `{TEMP_DIR}` |
| _parser home directory_ | In this directory parser storage own working immutable files. | `parsers/{PARSER}` |
| _parser output directory_ | In this directory parser saves parsing result from own source. In base contains `titles`, `images` and `content` subdirectories. | `{OUTPUT_DIR}/{PARSER}` |
| _parser temporary directory_ | It is used to store temporary files required by the parser or to download images without specifying a path. | `{TEMP_DIR}/{PARSER}` |

### ⚙️ Parsers
| **Term** | **Definition** |
|---|---|
| _collection_ | Text file that contains collection of titles slugs in `temp/{PARSER}/collections` directory. |
| _parser_ | Module for **Melon** that provides source operator and content parsing submodules (manga and ranobe workers). |
| _source operator_ | Parser main poit which works with source without being tied to a specific content type. |

### 💾 Data
| **Term** | **Definition** |
|---|---|
| _descriptive file_ | JSON file that created by **Melon** as parsing result. Stores title data locally. |
| _descriptive file format_ | Format of descriptive JSON file for content type: `melon-manga` or `melon-ranobe`. |
| _content branch_ | Sets of chapters that often overlap with each other and have undergone different processing (for example, different translation or editorial versions from various publishers). |
