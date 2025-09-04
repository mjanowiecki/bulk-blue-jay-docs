---
title: How to fill out archival object CSV
hide:
  - toc
---

# How to fill out archival object template CSV

:material-file-document: [Download blank template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/blank-templates/archival-object-template-blank.csv)

:material-file-document-check-outline: [Download example template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/example-templates/archival-object-template-example.csv)

## :octicons-light-bulb-16: Example of completed `archival_objects.csv`

| title                         | parent                                   | position | repository      | resource                       | level | publish | suppressed | restrictions\_apply | repository\_processing\_note                                                                                                        | dates                                                                  | extents                                                                                               | linked\_agents                                                                     | subjects                       | singlepart\_note                                                                                                                                | multipart\_note                                                                         | instances                                                                                                         |
|-------------------------------|------------------------------------------|----------|-----------------|--------------------------------|-------|---------|------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Audio recordings of blue jays | /repositories/3/archival\_objects/326200 | 1        | /repositories/3 | /repositories/3/resources/1821 | file  | True    | False      | False               |                                                                                                                                     | label==creation;;date\_type==inclusive;;begin==2003\-03;;end==2003\-12 | number==26;;portion==whole;;extent\_type==Items;;container\_summary==26 cassettes                     | role==creator;;ref==/agents/people/6453\|\|role==creator;;ref==/agents/people/6454 | /subjects/2437\|/subjects/2727 |                                                                                                                                                 | type==arrangement;;publish==True;;content==Arranged by identified bird\.                |                                                                                                                   |
| Blue jay feathers             | /repositories/3/archival\_objects/326200 | 3        | /repositories/3 | /repositories/3/resources/1821 | file  | True    | False      | False               | Please note that the actual feathers are held by the Department of Biology and cannot be accessed\. This file is photographs only\. | label==creation;;date\_type==single;;begin==2003                       | number==175;;portion==whole;;extent\_type==photographic\_prints;;container\_summary==175 color photos | role==creator;;ref==/agents/people/6453\|\|role==creator;;ref==/agents/people/6454 | /subjects/2730\|/subjects/2727 | type==physdesc;;publish==True;;content==175 photographs of 57 feathers\.                                                                        | type==arrangement;;publish==True;;content==Arranged by feather identifier\.             |                                                                                                                   |
| Research data and papers      | /repositories/3/archival\_objects/326200 | 4        | /repositories/3 | /repositories/3/resources/1821 | file  | True    | False      | False               |                                                                                                                                     | label==creation;;date\_type==inclusive;;begin==2001;;end==2004         | number==\.835;;container\_summary==4 folders;;portion==whole;;extent\_type==cubic\_feet               | role==creator;;ref==/agents/corporate\_entities/2018                               |                                | type==materialspec;;publish==True;;content==Includes drafts of the paper, “Are blue jays the rudest birds in Maryland? A scientific approach\.” | type==acqinfo;;publish==True;;content==Processed by Lauren McAwesomeSauce in May 2025\. | ref==/repositories/3/top\_containers/24636;;instance\_type==mixed\_materials;;type\_2==folder;;indicator\_2==1\-4 |



## :material-table-heart: CSV columns

### Columns related to `Organization`
??? note "parent"
    - ArchivesSpace field equivalent: *Where object is nested*
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)

??? note "position"
    - ArchivesSpace field equivalent: *Order of archival objects*
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: [Integer](../workflow/2-fill-out-templates.md/#integers)


??? note "resource"
    - ArchivesSpace field equivalent: *Collection ref*
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)


### Columns related to `Basic Information`
??? note "title"
    - ArchivesSpace field equivalent: Title
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

??? note "component_id"
    - ArchivesSpace field equivalent: Component Unique Identifier
    - Required in CSV: :x: False 
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

??? note "level"
    - ArchivesSpace field equivalent: Level of Description
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Archival Record Level

??? note "publish"
    - ArchivesSpace field equivalent: Publish?
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)

??? note "suppressed"
    - ArchivesSpace field equivalent: Supress button
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)

??? note "restrictions_apply"
    - ArchivesSpace field equivalent: Restrictions Apply?
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)

??? note "repository_processing_note"
    - ArchivesSpace field equivalent: Repository Processing Note
    - Required in CSV: :x: False
    - Allows multiple values: :x: False 
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

### Columns related to `Languages`
??? note "lang_materials"
    - ArchivesSpace field equivalent: 
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - language
            - ArchivesSpace field equivalent: Language
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Language ISO 639-2
        - script
            - ArchivesSpace field equivalent: Script
            - Required in field: :x: False
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Language ISO 15924
        - label
            - ArchivesSpace field equivalent: 
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - publish
            - ArchivesSpace field equivalent: Publish
            - Required in field: :x: False
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
        - content
            - ArchivesSpace field equivalent: Content
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `language==fre;;publish==True;;script==Latn;;content==All audio is in French.`

### Columns related to `Dates`
??? note "dates"
    - ArchivesSpace field equivalent: Dates section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields: 
        - label
            - ArchivesSpace field equivalent: Label
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Date Label
        - expression
            - ArchivesSpace field equivalent: Expression
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - date_type
            - ArchivesSpace field equivalent: Type
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Date Type
        - begin
            - ArchivesSpace field equivalent: 
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string) - YYYY, YYYY-MM, or YYYY-MM-DD
        - end
            - ArchivesSpace field equivalent: 
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string) - YYYY, YYYY-MM, or YYYY-MM-DD
        - certainty
            - ArchivesSpace field equivalent: 
            - Required in field: :x: False
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Date Certainty
    - Example: `label==creation;;date_type==single;;expression==2007 April 30;;begin==2007-04-30`

### Columns related to `Extents`
??? note "extents"
    - ArchivesSpace field equivalent: Extents section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type) 
    - Allowed subfields
        - portion
            - ArchivesSpace field equivalent: Portion
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Extent Portion
        - number
            - ArchivesSpace field equivalent: Number
            - Required in field: :white_check_mark: True
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - extent_type
            - ArchivesSpace field equivalent: Type
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Extent Extent Type
        - container_summary
            - ArchivesSpace field equivalent: Container Summary
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - physical_details
            - ArchivesSpace field equivalent: Physical Details
            - Required in field: :x: False
        -    Data type: String
        - dimensions
            - ArchivesSpace field equivalent: Dimensions
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `number==.167;;container_summary==1 folder;;portion==whole;;extent_type==cubic_feet`

### Columns related to `Agent Links`
??? note "linked_agents"
    - ArchivesSpace field equivalent: Agent Links section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - ref 
            - ArchivesSpace field equivalent: Agents
            - Required in field: :white_check_mark: True
            - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)
        - relator
            - ArchivesSpace field equivalent: Relator
            - Required in field: :x: False
            - Data type:[Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Linked Agent Archival Record Relators
        - role
            - - ArchivesSpace field equivalent: Role
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Linked Agent Role
    - Example: `role==creator;;relator==pht;;ref==/agents/corporate_entities/388`

### Columns related to `Accession Links`
??? note "accession_links"
    - ArchivesSpace field equivalent: Accession Links section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)
    - Example: `/repositories/3/accessions/120`

### Columns related to `Subjects`

??? note "subjects"
    - ArchivesSpace field equivalent: Subjects section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)
    - Example: `/subjects/2553|/subjects/551`

### Columns related to `Notes`
The type of note needed depends on your note type. 

Multipart type notes

- Conditions Governing Access
- Accruals
- Immediate Source of Acquisition
- Existence and Location of Copies
- Appraisal
- Arrangement
- Biographical / Historical
- Custodial History
- Dimensions 
- File Plan
- Legal Status
- General
- Existence and Location of Originals
- Other Finding Aids
- Physical Characteristics and Technical Requirements
- Preferred Citation 
- Processing Information
- Related Materials
- Scope and Contents
- Separated Materials
- Conditions Governing Use


Single type notes

- Abstract
- Materials Specific Details
- Physical Description
- Physical Facet
- Physical Location

??? note "multipart_note"
    - ArchivesSpace field equivalent: Multipart Note
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - note_type
            - ArchivesSpace field equivalent: Note Type
            - Required in field: :white_check_mark: True
            - Data type:[Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Note Multipart Type
        - publish
            - ArchivesSpace field equivalent: Publish
            - Required in field: :white_check_mark: True
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
        - content
            - ArchivesSpace field equivalent: Content
            - Required in field: :white_check_mark: True
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `type==materialspec;;publish==True;;content==Includes drafts of the paper, “Are blue jays the rudest birds in Maryland? A scientific approach.”`
    - Additional information: The note and subnote both receive their publish status from the field `publish`. At this time, the content subfield only accepts string/free-text values.

??? note "singlepart_note"
    - ArchivesSpace field equivalent: Single Part Note
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - note_type
            - ArchivesSpace field equivalent: Note Type
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Note Singlepart Type
        - publish
            - ArchivesSpace field equivalent: Publish
            - Required in field: :white_check_mark: True
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
        - content
            - ArchivesSpace field equivalent: Content
            - Required in field: :white_check_mark: True
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `type==physdesc;;publish==True;;content==175 photographs of 57 feathers.`
    - Additional information: The note and subnote both receive their publish status from the field `publish`. At this time, the content subfield only accepts string/free-text values.

### Columns related to `Instances`
??? note "instances"
    - ArchivesSpace field equivalent: Instances section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - instance_type
            - ArchivesSpace field equivalent: Type
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) -Instance Instance Type
        - is_representative
            - ArchivesSpace field equivalent: Is Representative?
            - Required in field: :x: False
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
        - ref
            - ArchivesSpace field equivalent: Top Container
            - Required in field: :white_check_mark: True
            - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)
        - type_2
            - ArchivesSpace field equivalent: Child Type
            - Required in field: :x: False
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Container Type
        - indicator_2
            - ArchivesSpace field equivalent: Child Indicator
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - barcode_2
            - ArchivesSpace field equivalent: Child Container Barcode
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - type_3
            - ArchivesSpace field equivalent: Grandchild Type
            - Required in field: :x: False
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Container Type
        - indicator_3
            - ArchivesSpace field equivalent: Grandchild Indicator
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `indicator_2==6;;ref==/repositories/3/top_containers/21451;;instance_type==mixed_materials;;type_2==folder;;is_representative==False`

## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postArchivalObjects.py` script.

- `'jsonmodel_type': 'archival_object'`
