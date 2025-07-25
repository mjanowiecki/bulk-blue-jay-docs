---
title: How to fill out top container CSV
hide:
  - toc
---

# How to fill out top container template CSV

:material-file-document: [Download blank template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/blank-templates/top-container-template-blank.csv)

:material-file-document-check-outline: [Download example template]()

## Example of completed `top_containers.csv`

| container_profile       | type   | indicator | barcode        | container_location                                           | internal_note     |
|-------------------------|--------|-----------|----------------|--------------------------------------------------------------|-------------------|
| /container_profiles/225 | box    | 34        | 41151034441778 |                                                              | Bound-with Box 12 |
| /container_profiles/145 | folder | 2         | 41151034444400 | status==current;;start_date==2019-07-18;;ref== /locations/37 |                   |
| /container_profiles/227 | item   | 4         | 41151084448799 |                                                              |                   |



## :material-table-heart: CSV columns

??? note "container_profile"
    - ArchivesSpace field equivalent: Container Profile
    - Required in CSV: :x: False
    - Allows multiple values: :x: False 
    - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)

??? note "type"
    - ArchivesSpace field equivalent: Container Type
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Container Type

??? note "indicator"
    - ArchivesSpace field equivalent: Indicator
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

??? note "barcode"
    - ArchivesSpace field equivalent: Barcode
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

??? note "internal_note"
    - ArchivesSpace field equivalent: Internal Note
    - Required in CSV: :x: False
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

### Columns related to `Locations`

??? note "container_location"
    - ArchivesSpace field equivalent: Locations section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - status
            - ArchivesSpace field equivalent: Status
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Container Location Status
        - start_date
            - ArchivesSpace field equivalent: Start Date
            - Required in field: :white_check_mark: True
            - Data type: [String](../workflow/2-fill-out-templates.md/#string) - YYYY-MM-DD
        - end_date
            - ArchivesSpace field equivalent: End Date
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string) - YYYY-MM-DD
        - note
            - ArchivesSpace field equivalent: Note
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - ref
            - ArchivesSpace field equivalent: Location
            - Required in field: :white_check_mark: True
            - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)

## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postTopContainers.py` script.

- `'jsonmodel_type': 'top_container'`
- `'publish': True`
- `'restricted': False`

If container location is added:

- `'jsonmodel_type': 'container_location'`
