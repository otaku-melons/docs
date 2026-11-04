# melon-ranobe
**melon-ranobe** – this is universal extendable Rolling-format for ranobe descriptive JSON files.

## Basic principles
* _**Chapters classification**_ – for content processors parsers should determine chapters types if this is possible.

### Chapter types
| **Chapter type** | **Description** |
|---|---|
| _afterword_ | Author or publisher afterword. |
| _art_ | Illustrations and additional images. |
| _chapter_ | Default chapter. |
| _epilogue_ | Epilogue. |
| _extra_ | Extra or bonus stories. |
| _glossary_ | Glossary or title universe description. |
| _prologue_ | Prologue. |
| _trash_ | Additional chapters with adversitement or workers notes. |

* _**Extendable**_ – parsers can extend basic struct by additional data. not described in this manifest.
* _**Independence**_ – format is completely independent of the sources and is not specific to any of them.
* _**Internationality**_ – content language specification is powered [ISO 639-3](https://iso639-3.sil.org/code_tables/639/data), localized name must be in same language.
* _**HTML**_ – only simple modern [HTML](HTML.md) tags are used for storage text data and styling support.
* _**Maximum clarity**_ – every field has pre‑determined type and valid values or, if no data, it is `null` or empty struct.
* _**Recognition of merit**_ – transloators, editors and other content workers details always parsed and storage if this info available.
* _**Rolling**_ – this format has no versions and can be changed without warnings and saving compatibility if this required for optimization, standardization or new impoerant 
* _**Synthetic ID**_ – if title, branch or chapter hasn't ID in source, it will be generated with two conditions: reproducibility and uniqueness in the source. 
* _**Typing by original language**_ – instead storage author's country format use original content language (this helps avoid frequent confusion between novels from the USA, the UK and other English‑speaking regions).
* _**Unambiguous statuses**_ – used only main and informative statuses (without separation into publication and translation statuses).

### Statuses
| **Status** | **Description** |
|---|---|
| _announced_ | Title announced and has no public available content or has only introductory chapters. |
| _ongoing_ | Title has regular chapters releases on content language. |
| _completed_ | Title fully published and translation done if necessary. |
| _dropped_ | Title dropped by author or workers. |

* _**Unified typing**_ – all titles belong to a certain type.

### Types
| **Type** | **Description** |
|---|---|
| _manga_ | Japanese manga. |
| _manhwa_ | Korean manhwa. |
| _manhua_ | China manhua. |
| _oel_ | Original english‑language manga (drawn by non‑japanese authors under the influence of manga).|
| _western_comic_ | Western comics. |
| _russian_comic_ | Russian comics. |
| _indonesian_comic_ | Indonesian comics. |

## Example
```json
{
	"format": "melon-ranobe",
	"domain": "example.com",
	"id": 123,
	"slug": "ranobe_slug",
	"content_language": "rus",
	"localized_name": "Название ранобэ",
	"eng_name": "Ranobe name",
	"another_names": [
		"Ranobe mei"
	],
	"covers": [
		{
			"link": "https://example.com/manga_slug/cover.jpg",
			"file": "covers/cover.jpg",
			"width": 720,
			"height": 1280
		}
	],
	"authors": [
		"Author name"
	],
	"publication_year": 2024,
	"description": [
		"<p style=\"text-align: right\">War is never changes.</p>",
		"<p>Description text with basic <b>styling</b>.</p>"
	],
	"age_limit": 16,
	"status": "ongoing",
	"is_licensed": false,
	"genres": [
		"genre"
	],
	"tags": [
		"tag"
	],
	"franchises": [
		"franchise"
	],
	"persons": [
		{
			"name": "Person name",
			"another_names": ["Alternative person name"],
			"images": [
				{
					"link": "https://example.com/person_slug/image.jpg",
					"file": "persons/image.jpg",
					"width": 480,
					"height": 480
				}
			],
			"description": [
				"<p>This is a cool person description with <i>italic</i> styled word.</p>"
			]
		}
	],
	"branches": [
		{
			"id": 123456,
			"chapters_count": 1
		}
	],
	"content": {
		"123456": [
			{
				"id": 1,
				"slug": "vol1-ch1",
				"volume": "1",
				"number": "1",
				"name": "Chapter name",
				"type": "chapter",
				"is_paid": false,
				"workers": [
					"Translator",
					"Editor"
				],
				"paragraphs": [
					"<h3 style=\"text-align: center\">Заголовок</h3>"
					"<p>Абзац со сноской<a data-footnote=\"41b34c39-72c8-43ad-84ab-3616ab383921\">*</a>.</p>",
					"<p>Абзац со <b><u>стилями</u></b>.</p>",
					"<blockquote data-name=\"Письмо\"><p>Текст письма.</p></blockquote>",
					"<img src=\"https:example.com/image1.png\" data-file=\"illustrations/image1.png\">"
				],
				"footnotes": {
					"41b34c39-72c8-43ad-84ab-3616ab383921": [
						"<p>Текст пояснения.</p>",
						"<img width=\"640\" height=\"480\" src=\"https:example.com/image2.png\" data-file=\"illustrations/image2.png\">"
					]
				}
			}
		]
	}
}
```
