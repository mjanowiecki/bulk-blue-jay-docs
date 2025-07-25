---
title: How to fill out subject template CSV
hide:
  - toc
---

# How to fill out subject template CSV

:material-file-document: [Download blank template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/blank-templates/subject-template-blank.csv)

:material-file-document-check-outline: [Download example template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/example-templates/subject-template-example.csv)

## :octicons-light-bulb-16: Example of completed `subject.csv`

| authority_id                              | source | term                         | term_type  |
|:------------------------------------------|:-------|:-----------------------------|:-----------|
| http://id.worldcat.org/fast/834963        | fast   | Blue Jay                     | topical    |
| http://id.worldcat.org/fast/1048358       | fast   | Ornithology                  | topical    |
| http://id.worldcat.org/fast/1755024       | fast   | Hurricane Isabel (2003)      | topical    |
| http://vocab.getty.edu/page/aat/300400474 | aat    | feathers (animal components) | genre_form |
| http://vocab.getty.edu/page/aat/300310080 | aat    | microcassettes               | genre_form |

## :material-table-heart: CSV columns

### Columns related to `Basic Information`

??? note "authority_id"
    - ArchivesSpace field equivalent: Authority ID   
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string) - External URI

??? note "source"
    - ArchivesSpace field equivalent:  
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Subject Source

### Columns related to `Terms and Subdivisions`

??? note "term"
    - ArchivesSpace field equivalent: Term  
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

??? note "term_type"
    - ArchivesSpace field equivalent: Term  
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Subject Term Type


## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postSubjects.py` script.

- `'jsonmodel_type': 'subject'`
- `'jsonmodel_type': 'term'`
- `'vocabulary': '/vocabularies/1'`
- `'publish': True`

