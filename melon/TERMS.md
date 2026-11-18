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
| _dependencies_ | Dependencies from components (Melon and parent parsers). |
| _parser_ | Module for **Melon** that provides source operator and content parsing submodules (manga and ranobe workers). |
| _requirements_ | Extra Python libs from `requirements.txt` in parser's home directory. |
| _source operator_ | Parser main point which works with source without being tied to a specific content type. |

### 🧩 Extensions
| **Term** | **Definition** |
|---|---|
| _extension identifier_ | Extension identifier is a string in `{PARSER}.{EXTENSION_NAME}` format. |
| _extension name_ | Extension name is unique for one parser string, second part of the identifier. |
| _package name_ | Same as identifier, but used in Python imports and have `{PARSER}_{EXTENSION_NAME}` format. |

### 💾 Data
| **Term** | **Definition** |
|---|---|
| _chapter header_ | Chapter header with numeration data (`Chapter 1. Some name` is header, `Some name` is name). |
| _content branch_ | Sets of chapters that often overlap with each other and have undergone different processing (for example, different translation or editorial versions from various publishers). |
| _descriptive file_ | JSON file that created by **Melon** as parsing result. Stores title data locally. |
| _descriptive file format_ | Format of descriptive JSON file for content type: `melon-manga` or `melon-ranobe`. |
| _title attributes_ | Title genres, tags, franchises and persons. |
| _title genre_ | Primary category of a title that defines it's format and narrative rules. It answers «What is this book overall?» (e.g., since fiction, romance). |
| _title tag_ | Values used to filter content by specific elements. It answers «What is inside?» (e.g., vampires, time travel). |

### 🎨 HTML
In Melon for HTML parsing [BeautifulSoup](https://pypi.org/project/beautifulsoup4) used. All HTML tags is an instances of this libruary objects.
| **Term** | **Definition** |
|---|---|
| _tag_ | HTML tag parsed with [BeautifulSoup](https://pypi.org/project/beautifulsoup4). |
| _element_ | Melon HTML element with valid struct such as `Paragraph` or `Blockquote`. |
| _line_ | String from JSON descriptive file with valid for Melon HTML markup. |
