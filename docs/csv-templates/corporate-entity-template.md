---
title: How to fill out corporate entity template CSV
---

# How to fill out corporate entity template CSV

:material-file-document: [Download blank template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/blank-templates/corporate-entity-blank.csv)

:material-file-document-check-outline: [Download example template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/example-templates/corporate-entity-example.csv)

## Example of completed `corporate_entity.csv`

| sort_name                                                                                                       | publish_corporate_body | source | rules | authority_id                                      | primary_name                   | subordinate_name_1                    | subordinate_name_2                       | number | dates | location      | conference_meeting | jurisdiction | qualifier | dates_of_existence                                                                  | notes                                                                                                                                                                                                                                              |
|-----------------------------------------------------------------------------------------------------------------|------------------------|--------|-------|---------------------------------------------------|--------------------------------|---------------------------------------|------------------------------------------|--------|-------|---------------|--------------------|--------------|-----------|-------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quercus Research Group (Firm)                                                                                   | TRUE                   | viaf   | rda   | http://viaf.org/viaf/example_004                  | Quercus Research Group         |                                       |                                          |        |       |               | FALSE              | FALSE        | Firm      | date_type_structured==range;;begin_date_expression==1990;;end_date_expression==2022 | notes_type==bioghist;;publish_note==True;;subnote_Type==text;;content==Quercus Research Group was formed in 1990 to research songbirds in the Mid-Atlantic region and published a scientific journal yearly until the group’s dissolution in 2022. |
| Gunpowder Falls State Park                                                                                      | TRUE                   | naf    | aacr  | http://id.loc.gov/authorities/names/noexample0032 | Gunpowder Falls State Park     |                                       |                                          |        |       |               | FALSE              | FALSE        |           |                                                                                     |                                                                                                                                                                                                                                                    |
| U.S. Fish and Wildlife Service. Division of Migratory Bird Management. Branch of Monitoring and Data Management | TRUE                   | viaf   | rda   | http://viaf.org/viaf/example_110                  | U.S. Fish and Wildlife Service | Division of Migratory Bird Management | Branch of Monitoring and Data Management |        |       |               | FALSE              | FALSE        |           |                                                                                     |                                                                                                                                                                                                                                                    |
| Birds of a Feather 5k (1st : 2003 : Brunswick, Md.)                                                             | TRUE                   | local  | local |                                                   | Birds of a Feather 5k          |                                       |                                          | 1st    | 2003  | Brunswick, Md | FALSE              | FALSE        |           |                                                                                     |                                                                                                                                                                                                                                                    |

## :material-table-heart: CSV columns

### Columns specific to workflow

??? note "sort_name"
    - While this is automatically generated during ingest, it is important to have it in the spreadsheet for matching with pre-existing names in step 4.
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: String

### Columns related to `Basic Information`

??? note "publish_corporate_entity"
    - ArchivesSpace field equivalent: Publish
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: Boolean

### Columns related to `Identity Information: Name Forms`
??? note "authority_id"
    - ArchivesSpace field equivalent: Authority ID   
    - Required in CSV: :x: False
    - Allows multiple values: :x: False 
    - Data type: String - External URI

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

??? note "primary_name"
    - ArchivesSpace field equivalent: Primary Part of Name
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: String

??? note "subordinate_name_1"
    - ArchivesSpace field equivalent: Subordinate Name 1
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "subordinate_name_2"
    - ArchivesSpace field equivalent: Subordinate Name 2
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "number"
    - ArchivesSpace field equivalent: Number
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "dates"
    - ArchivesSpace field equivalent: Dates
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "location"
    - ArchivesSpace field equivalent: Location
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

??? note "conference_meeting"
    - ArchivesSpace field equivalent: Conference Meeting?
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: Boolean

??? note "jurisdiction"
    - ArchivesSpace field equivalent: Jurisdiction?
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: Boolean

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
            - Data type: YYYY-MM-DD
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
            - Data type: String - YYYY-MM-DD
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
    - Example: `note_type==bioghist;;publish==TRUE;;content==Choreographer and artistic directory of the Peabody Preparatory dance department, circa 1985-2010.`

## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postCorporateAgents.py` script.

- `'jsonmodel_type': 'agent_corporate_entity'`
- `'jsonmodel_type': 'name_corporate_entity'`
- `'sort_name_auto_generate': True`
- `'authorized': True`
- `'is_display_name': True`
