---
title: Fill out CSV templates for ArchivesSpace entities
---

For your collection, create spreadsheets for the following types of entities according to our template guidelines. These templates assume that you will create the main resource for the collection manually.

## Available CSV templates
- [:material-file-document: Archival object template](../csv-templates/archival-object-template.md)
- [:material-tie: Corporate entity template](../csv-templates/corporate-entity-template.md)
- [:fontawesome-solid-floppy-disk: Digital object template](../csv-templates/digital-object-template.md)
- [:fontawesome-solid-user-group: Family template](../csv-templates/family-template.md)
- [:fontawesome-solid-user: Person template](../csv-templates/person-template.md)
- [:material-flower-poppy: Subject template](../csv-templates/subject-template.md)
- [:material-file-cabinet: Top container template](../csv-templates/top-container-template.md)

## Template limitations 

### :material-exclamation: Not all metadata fields available in template. 

While we tried to have the CSVs templates include as many metadata fields as possible, there are many we were not able to add at this time. If a field isn't in template, you can only add it by changing both the templates and the relevant scripts.

### :material-repeat-off: Some metadata fields are not repeatable in the template

Some metadata fields are not repeatable in the template, even if ArchivesSpace allows repeatability.
For some paired fields, which only make sense together, like `authority_id` and `source_id` -- we have chosen not to make repeatable to make the template easier to use. We understand this isn't ideal and may change it in the future.

## Formatting and encoding in CSVs

### :fontawesome-regular-keyboard: Encoding
- If given the option by your spreadsheet editor, always encode your CSV as UTF-8.
- If possible, format all of your cells as `Plain Text` or `Text` before saving/exporting as a CSV. This will prevent automatic formatting in most spreadsheet editors.

### :fontawesome-solid-spell-check: Diacritics
Do not simply enter diacritics and other special characters into your spreadsheets, as these cannot be properly read by ArchivesSpace for some horrible reason. Instead, use HTML character codes, which can be found online and have the pattern $#\[number\].

### :material-table-column: Column rules

- Columns can be in any order in the template.
- Unless required, unused columns do not need to be included in your template.
- Column headings must be spelled exactly as prescripted in the template with the same capitalization.

## Data Types

The data types given in the CSV template indicate what type of value is needed by the Python scripts to successfully ingest new records into ArchivesSpace. It does not, however, always enforce ArchivesSpace rules, formatting, or best practices. For instance, if best practices determine that URL is always desired in a specific field, and you enter `blah mondays are the worst` instead, the script will mostly likely still work, creating a new record with the value of `blah mondays are the worst` in that field.

### :fontawesome-solid-keyboard: String
Any characters can be entered in this cell, including numbers, letters, and symbols. For instance, a URL, barcode, or a paragraph of text would be accepted as string values.

### :fontawesome-solid-list: Controlled List

Only values from the specified controlled list can be used. To find see the accepted values, either navigate to  `System → Controlled Value lists` in the staff interface of ArchivesSpace or view your `enumerations.csv` -- the name of the Controlled List is in column `Enumeration` and the accepted values are in column `Value code.` 

| Enumeration code | Enumeration    | Value code | Value                                                                             | Position | Read-only |
|------------------|----------------|------------|-----------------------------------------------------------------------------------|----------|-----------|
| subject_source   | Subject Source | aat        | Art & Architecture Thesaurus                                                      | 0        | 0         |
| subject_source   | Subject Source | fast       | fast                                                                              | 1        | 0         |
| subject_source   | Subject Source | gmgpc      | TGM II, Genre and physical characteristic terms                                   | 2        | 0         |
| subject_source   | Subject Source | lcsh       | Library of Congress Subject Headings                                              | 3        | 0         |
| subject_source   | Subject Source | local      | Local sources                                                                     | 4        | 0         |
| subject_source   | Subject Source | mesh       | Medical Subject Headings                                                          | 5        | 0         |

For instance, if the Controlled List given for a column is `Subject Source`, acceptable values would include:

- :octicons-check-circle-16: aat
- :octicons-check-circle-16: fast
- :octicons-check-circle-16: local

Values like the following, containing typos or different capitalization, will not work properly.

- :octicons-x-circle-16: FAST
- :octicons-x-circle-16: Medical Subject Headings
- :octicons-x-circle-16: gmgpc
- :octicons-x-circle-16: Aat

### :material-checkbox-outline: Boolean

The only accepted values in these fields are `TRUE` or `FALSE`.

### :material-link: Ref

The only accepted values in these fields are URIs from your local ArchivesSpace instance. Do not include the "base" component of the URI.

Examples:

- `/agents/corporate_entities/879`
- `/subjects/339`
- `/repositories/3/archival_objects/84637`

### :material-format-list-group-plus: Subfield type

This data type is specific to the Big Blue Jay workflow templates and helps us represent fields with multiple subfields. Each subfield is linked to its value by "==". For instance, the `linked_agents` field has three subfields: `role`, `relator`, and `ref`. This means a corporate entity with the role of creator and the relator would be formatted as followed:

`role==creator;;relator==pht;;ref==/agents/corporate_entities/388`

If the field needs to be repeated, each field is separated by double pipes (`||`). For instance:

`role==creator;;relator==pht;;ref==/agents/corporate_entities/388||role==creator;;relator==edt;;ref==/agents/corporate_entities/698`

The subfields can be in any order in the spreadsheet. Subfields that are not required do not need to be included in spreadsheet.
