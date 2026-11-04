# melon-manga
**melon-manga** – this is universal extendable Rolling-format for manga descriptive JSON files.

## Basic principles
* _**Extendable**_ – parsers can extend basic struct by additional data. not described in this manifest.
* _**Independence**_ – format is completely independent of the sources and is not specific to any of them.
* _**Internationality**_ – content language specification is powered [ISO 639-3](https://iso639-3.sil.org/code_tables/639/data), localized name must be in same language.
* _**HTML**_ – only simple modern [HTML](HTML.md) tags are used for storage text data and styling support.
* _**Maximum clarity**_ – every field has pre‑determined type and valid values or, if no data, it is `null` or empty struct.
* _**Recognition of merit**_ – transloators, editors and other content workers details always parsed and storage if this info available.
* _**Rolling**_ – this format has no versions and can be changed without warnings and saving compatibility if this required for optimization, standardization or new impoerant 
* _**Slide indexes from 1**_ – first slide index always is 1, because of it comfortable for humans interpretation.
* _**Synthetic ID**_ – if title, branch or chapter hasn't ID in source, it will be generated with two conditions: reproducibility and uniqueness in the source. 
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
	"format": "melon-manga",
	"domain": "example.com",
	"id": 123,
	"slug": "manga_slug",
	"content_language": "rus",
	"localized_name": "Название манги",
	"eng_name": "Manga name",
	"another_names": [
		"Manga mei"
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
	"type": "manga",
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
				"is_paid": false,
				"workers": [
					"Translator",
					"Editor"
				],
				"slides": [
					{
						"index": 1,
						"link": "https://example.com/manga_slug/vol1_ch1/1.jpg",
						"file": null,
						"width": 1080,
						"height": 1920
					}
				]
			}
		]
	}
}
```
