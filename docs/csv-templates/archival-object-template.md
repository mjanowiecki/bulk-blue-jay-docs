---
title: How to fill out archival object CSV
---

# How to fill out archival object template CSV

:material-file-document: [Download blank template]()

:material-file-document-check-outline: [Download example template]()

## :octicons-light-bulb-16: Example of completed `archival_objects.csv`



## :material-table-heart: CSV columns

### Columns related to `Organization`
??? note "parent"
    - ArchivesSpace field equivalent: *Where object is nested*
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: Ref

??? note "position"
    - ArchivesSpace field equivalent: *Order of archival objects*
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: Integer

??? note "other_level"
    - ArchivesSpace field equivalent: Other Level
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: String

### Columns related to `Basic Information`
??? note "title"
    - ArchivesSpace field equivalent: Title
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: String

??? note "resource"
    - ArchivesSpace field equivalent:
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: Ref

??? note "component_id"
    - ArchivesSpace field equivalent: Component Unique Identifier
    - Required in CSV: :x: False 
    - Allows multiple values: :x: False 
    - Data type: String

??? note "level"
    - ArchivesSpace field equivalent: Level of Description
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: Controlled list - Archival Record Level

??? note "publish"
    - ArchivesSpace field equivalent: Publish?
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: Boolean 

??? note "suppressed"
    - ArchivesSpace field equivalent: Supress button
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: Boolean

??? note "restrictions_apply"
    - ArchivesSpace field equivalent: Restrictions Apply?
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: Boolean

??? note "repository_processing_note"
    - ArchivesSpace field equivalent: Repository Processing Note
    - Required in CSV: :x: False
    - Allows multiple values: :x: False 
    - Data type: String

### Columns related to `Dates`
??? note "dates"
    - ArchivesSpace field equivalent: Dates section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type
    - Allowed subfields: 
        - label
            - ArchivesSpace field equivalent: Label
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Date Label
        - expression
            - ArchivesSpace field equivalent: Expression
            - Required in field: :x: False
            - Data type: String
        - date_type
            - ArchivesSpace field equivalent: Type
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Date Type
        - begin
            - ArchivesSpace field equivalent: 
            - Required in field: :x: False
            - Data type: String - YYYY, YYYY-MM, or YYYY-MM-DD
        - end
            - ArchivesSpace field equivalent: 
            - Required in field: :x: False
            - Data type: String - YYYY, YYYY-MM, or YYYY-MM-DD
        - certainty
            - ArchivesSpace field equivalent: 
            - Required in field: :x: False
            - Data type: Controlled list - Date Certainty
    - Example: `label==creation;;date_type==single;;expression==2007 April 30;;begin==2007-04-30`

### Columns related to `Extents`
??? note "extents"
    - ArchivesSpace field equivalent: Extents section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type 
    - Allowed subfields
        - portion
            - ArchivesSpace field equivalent:
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Extent Portion
        - number
            - ArchivesSpace field equivalent:
            - Required in field: :white_check_mark: True
            - Data type: String
        - type
            - ArchivesSpace field equivalent:
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Extent Extent Type
        - container_summary
            - ArchivesSpace field equivalent:
            - Required in field: :x: False
            - Data type: String
        - physical_details
            - ArchivesSpace field equivalent:
            - Required in field: :x: False
        -    Data type: String
        - dimensions
            - ArchivesSpace field equivalent:
            - Required in field: :x: False
            - Data type: String
    - Example:

### Columns related to `Agent Links`
??? note "linked_agents"
    - ArchivesSpace field equivalent: Agent Links section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type
    - Allowed subfields:
        - ref 
            - ArchivesSpace field equivalent: Agents
            - Required in field: :white_check_mark: True
            - Data type: Ref
        - relator
            - ArchivesSpace field equivalent: Relator
            - Required in field: :x: False
            - Data type: Controlled list - Linked Agent Archival Record Relators
        - role
            - - ArchivesSpace field equivalent: Role
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Linked Agent Role
    - Example: `role==creator;;relator==pht;;ref==/agents/corporate_entities/388`

### Columns related to `Accession Links`
??? note "accession_links"
    - ArchivesSpace field equivalent: Accession Links section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Ref
    - Example: `/repositories/3/accessions/120`

### Columns related to `Subjects`

??? note "subjects"
    - ArchivesSpace field equivalent: Subjects section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Ref
    - Example: `/subjects/2553|/subjects/551`

### Columns related to `Notes`
??? note "multipart_note"
    - ArchivesSpace field equivalent: Multipart Note
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type
    - Allowed subfields:
        - note_type
            - ArchivesSpace field equivalent: Note Type
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Note Multipart Type
        - publish
            - ArchivesSpace field equivalent: Publish
            - Required in field: :white_check_mark: True
            - Data type: Boolean
        - content
            - ArchivesSpace field equivalent: Content
            - Required in field: :white_check_mark: True
            - Data type: String
    - Example: 

??? note "singlepart_note"
    - ArchivesSpace field equivalent: Single Part Note
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type
    - Allowed subfields:
        - note_type
            - ArchivesSpace field equivalent: Note Type
            - Required in field: :white_check_mark: True
            - Data type: Controlled list - Note Singlepart Type
        - publish
            - ArchivesSpace field equivalent: Publish
            - Required in field: :white_check_mark: True
            - Data type: Boolean
        - content
            - ArchivesSpace field equivalent: Content
            - Required in field: :white_check_mark: True
            - Data type: String

??? note "lang_materials"

### Columns related to `Instances`
??? note "instances"
    - ArchivesSpace field equivalent: Instances section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: Subfield type
    - Allowed subfields:
        - type
            - ArchivesSpace field equivalent: Type
            - Required in field: :white_check_mark: True
            - Data type: Controlled list
        - top_container
            - ArchivesSpace field equivalent: Type
            - Required in field: :white_check_mark: True
            - Data type: ref
        - child_type
            - ArchivesSpace field equivalent: Child Type
            - Required in field: :x: False
            - Data type: Controlled list
        - child_indicator
            - ArchivesSpace field equivalent: Child Indicator
            - Required in field: :x: False
            - Data type: String
        - child_container_barcode
            - ArchivesSpace field equivalent: Child Container Barcode
            - Required in field: :x: False
            - Data type: String
        - grandchild_type
            - ArchivesSpace field equivalent: Grandchild Type
            - Required in field: :x: False
            - Data type: Controlled list
        - grandchild_indicator
            - ArchivesSpace field equivalent: Grandchild Indicator
            - Required in field: :x: False
            - Data type: String
    - Example: 

## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postArchivalObjects.py` script.

- `'jsonmodel_type': 'archival_object'`
