---
title: How to fill out family template CSV
---

# How to fill out family template CSV

:material-file-document: [Download blank template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/blank-templates/family-template-blank.csv)

:material-file-document-check-outline: [Download example template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/example-templates/family-template-example.csv)

## :octicons-light-bulb-16: Example of completed `family.csv`
| sort_name                     | publish_family | authority_id                          | source | rules | family_name | dates | family_type | location | qualifier | dates_of_existence                                       | notes                                                                                                                                                                 |
|-------------------------------|----------------|---------------------------------------|--------|-------|-------------|-------|-------------|----------|-----------|----------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ptak family, 1992- (Maryland) | TRUE           | http://viaf.org/viaf/example00402     | viaf   | rda   | Ptak family | 1992- |             | Maryland |           | date_type_structured==range;;begin_date_expression==1992 | notes_type==bioghist;;publish_note==True;;subnote_Type==text;;content==The Ptak family are known regionally for their donations to conservations and climate efforts. |
| Fugl family                   | TRUE           | https://viaf.org/en/viaf/example01065 | viaf   | aacr  | Fugl family |       |             |          |           |                                                          |                                                                                                                                                                       |


## :material-table-heart: CSV columns

### Columns specific to workflow
??? note "sort_name"
    - While this is automatically generated during ingest, it is important to have it in the spreadsheet for matching with pre-existing names in step 4.
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: String

### Columns related to `Basic Information`

??? note "publish_family"
    - ArchivesSpace field equivalent: Publish
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: Boolean

### Columns related to `Identity Information: Name Forms`
??? note "authority_id"
    - ArchivesSpace field equivalent: Authority ID   
    - Required in CSV: :x: False
    - Allows multiple values: :x: False 
    - Data type: String

??? note "source"
    - ArchivesSpace field equivalent:  Source
    - Required in CSV: :x: False
    - Allows multiple values: :x: False 
    - Data type: Controlled list - Name Source 

??? note "rules"
    - ArchivesSpace field equivalent: Rules
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: Controlled list - Name Rule

??? note "family_name"
    - ArchivesSpace field equivalent: Family Name
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: String

??? note "dates"
    - ArchivesSpace field equivalent: Dates
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "family_type"
    - ArchivesSpace field equivalent: Family Type
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "location"
    - ArchivesSpace field equivalent: Location
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "qualifier"
    - ArchivesSpace field equivalent: Qualifier
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

### Columns related to `Description Information: Dates of Existence`

??? note "dates_of_existence"
    - ArchivesSpace field equivalent: Dates of Existence section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type
    - Allowed subfields: 
        - date_type_structured
            - ArchivesSpace field equivalent: Date Type
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Date Type Structured
        - date_certainty
            - ArchivesSpace field equivalent: Certainty
            - Required in field: :x: False
            - Data type: Controlled list - Date Certainty
        - date_role
            - ArchivesSpace field equivalent: Single Date - Date Role
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Date Role
        - date_expression
            - ArchivesSpace field equivalent: Single Date - Date Expression
            - Required in field: :x: False
            - Data type: String
        - date_standardized
            - ArchivesSpace field equivalent: Single Date - Standardized Date
            - Required in field: :x: False
            - Data type: String - YYYY-MM-DD
        - date_standardization_type
            - ArchivesSpace field equivalent: Single Date - Standardized Date Type
            - Required in field: :x: False
            - Data type: Controlled list - Date Standardization Type
        - begin_date_expression
            - ArchivesSpace field equivalent: Range Date - Begin Date Expression
            - Required in field: :x: False
            - Data type: String
        -begin_date_standardized
            - ArchivesSpace field equivalent: Range Date - Begin Standardized Date
            - Required in field: :x: False
            - Data type: YYYY-MM-DD
        - begin_date_standardized_type
            - ArchivesSpace field equivalent: Range Date - Begin Standardized Date Type
            - Required in field: :x: False
            - Data type: Controlled list - Begin Date Standardized Type
        - end_date_expression
            - ArchivesSpace field equivalent: Range Date - End Date Expression
            - Required in field: :x: False
            - Data type: String
        - end_date_standardized
            - ArchivesSpace field equivalent: Range Date - End Standardized Date
            - Required in field: :x: False
            - Data type: String - YYYY-MM-DD
        - end_date_standardized_type
            - ArchivesSpace field equivalent: Range Date - End Standardized Date Type
            - Required in field: :x: False
            - Data type: Controlled list - End Date Standardized Type
    - Example: `date_type_structured==range;;date_certainty==approximate;;begin_date_expression==1985;;end_date_expression==2010`

### Columns related to `Description Information: Notes`
??? note "notes"
    - ArchivesSpace field equivalent: Single Part Note
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type
    - Allowed subfields:
        - note_type
            - ArchivesSpace field equivalent: Note Type
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - 
        - publish
            - ArchivesSpace field equivalent: Publish
            - Required in field: :white_check_mark: True
            - Data type: Boolean
        - content
            - ArchivesSpace field equivalent: Content
            - Required in field: :white_check_mark: True
            - Data type: String
    - Additional information: The note and subnote both receive their publish status from the field `publish`. At this time, only plain text is accepted as a subnote.
    - Example: `note_type==bioghist;;publish==TRUE;;content==Sir Jay Azul Jr. II was born in Portland, Maine. He worked on ornithology projects at seven universities throughout his career.`

## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postFamily.py` script.

- `'jsonmodel_type': 'agent_family'`
- `'jsonmodel_type': 'name_family'`
- `'agent_type' : 'agent_family'`
- `'sort_name_auto_generate': True`
- `'authorized': True`
- `'is_display_name': True`
