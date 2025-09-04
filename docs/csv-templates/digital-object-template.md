---
title: How to fill out digital object template CSV
hide:
  - toc
---
# How to fill out digital object template CSV
:material-file-document: [Download blank template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/blank-templates/digital-object-template-blank.csv)

:material-file-document-check-outline: [Download example template](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/csv-templates/digital-templates/archival-object-template-example.csv)

## :octicons-light-bulb-16: Example of completed `digital_objects.csv`

| publish | title                                                              | digital_object_id | restrictions | suppressed | digital_object_type | file_versions                                                                                                                                                             | lang_materials              | dates                                                                               | extents                                                                                                   | agent_links                                                                                     | subjects                 | notes                                                                                                                                                                                                                                                                                         |
|---------|--------------------------------------------------------------------|-------------------|--------------|------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|-------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TRUE    | Digital photographs of blue jay                                    | EX-0001_001       | FALSE        | FALSE      | still_image         | file_uri==u:/collections/EX-001/digital_objects/photographs;;publish==TRUE;;is_representative==FALSE                                                                      |                             | label==creation;;date_type==inclusive;;begin==2003-03;;end==2003-12                 | portion==whole;;number==8.78;;type==gigabytes;;container_summary==Disk EX-001_001;;physical_details==tiff | role==creator;;ref==Azul, Sir Jay Jr. II\|role==creator;;ref==Bleue, K.C. (Krista Clara), 1973- | microcassettes\|Blue jay | type==summary;;content==These photographs are part of the Blue Jay Example Collection, id EX-0001.;;publish==TRUE\|\|type==accessrestrict;;content==A digital copy of the photographs are available for access upon request. Contact Special Collections for more information.;;publish==TRUE |
| TRUE    | Digitized audio recordings of blue jays                            | EX-0001_002       | FALSE        | FALSE      | sound_recording     | file_uri==u:/collections/EX-001/digital_objects/sound_recordings;;is_representative==FALSE;;publish==TRUE                                                                 | language==eng;;script==Latn | label==creation;;date_type==inclusive;;begin==2003;;end==2004                       | portion==whole;;number==25;;type==gigabytes;;container_summary==Disk EX-001_001;;physical_details==mp3    | role==creator;;ref==Azul, Sir Jay Jr. II\|role==creator;;ref==Bleue, K.C. (Krista Clara), 1973- | photographs\|Blue jay    | type==accessrestrict;;content==A digital copy of the audio files are available for access upon request. Contact Special Collections for more information.;;publish==TRUE                                                                                                                      |
| FALSE   | Are blue jays the rudest birds in Maryland? A scientific approach. | EX-0001_003       | TRUE         | FALSE      | text                | file_uri==u:/collections/EX-001/digital_objects/rudest_bird.pdf;;publish==TRUE;;is_representative==FALSE;;identifier==123;;caption==Scanned pdf of submitted final draft. | language==eng;;script==Latn | label==creation;;date_type==single;;begin==2003-11-01;;expression==2003 November 01 |                                                                                                           | role==creator;;ref==Azul, Sir Jay Jr. II                                                        |                          | type==accessrestrict;;content==A digital copy of the paper is available for access upon request. Contact Special Collections for more information.;;publish==TRUE                                                                                                                             |

## :material-table-heart: CSV columns

### Columns specific to workflow

### Columns related to `Basic Information`
??? note "publish"
    - ArchivesSpace field equivalent: Publish?
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False 
    - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)

??? note "title"
    - ArchivesSpace field equivalent: Title
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

??? note "digital_object_id"
    - ArchivesSpace field equivalent: Identifier
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: [String](../workflow/2-fill-out-templates.md/#string)

??? note "restrictions"
    - ArchivesSpace field equivalent: Restrictions?
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)

??? note "suppressed"
    - ArchivesSpace field equivalent: Yellow Suppress button
    - Required in CSV: :white_check_mark: True
    - Allows multiple values: :x: False
    - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)

??? note "digital_object_type"
    - ArchivesSpace field equivalent: Type
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Digital Object Digital Object Type

### Columns related to `File Versions`

??? note "file_versions"
    - ArchivesSpace field equivalent: File Versions
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - file_uri
            - ArchivesSpace field equivalent: File URI
            - Required in field: :white_check_mark: True
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - publish            
            - ArchivesSpace field equivalent: Publish?
            - Required in field: :x: False
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
        - caption
            - ArchivesSpace field equivalent: Caption
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - is_representative
            - ArchivesSpace field equivalent: Make Representative button
            - Required in CSV: :x: False
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
        - identifier
            - ArchivesSpace field equivalent: Identifier
            - Required in CSV: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `file_uri==http://jhir.library.jhu.edu/handle/1774.2/63642;;publish==TRUE;;is_represenative==FALSE`

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
            - ArchivesSpace field equivalent: Label
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - publish
            - ArchivesSpace field equivalent: Publish?
            - Required in field: :x: False
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
        - content
            - ArchivesSpace field equivalent: Content
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `language==fre;;publish==True;;script==Latn;;content==All audio is in French.`

### Columns related to `Dates`

??? note "dates"
    - ArchivesSpace field equivalent: Dates
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
            - ArchivesSpace field equivalent: Begin
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string) - YYYY, YYYY-MM, or YYYY-MM-DD
        - end
            - ArchivesSpace field equivalent: End
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string) - YYYY, YYYY-MM, or YYYY-MM-DD
        - certainty
            - ArchivesSpace field equivalent: Certainty
            - Required in field: :x: False
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Date Certainty
    - Example: `label==creation;;expression==2000-2010;;date_type==inclusive;;begin==2000;;end==2010`

### Columns related to `Extents`

??? note "extents"
    - ArchivesSpace field equivalent: Extents
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields: 
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
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - dimensions
            - ArchivesSpace field equivalent: Dimensions
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
    - Example: `portion==whole;;number==4.4;;extent_type==gigabytes;;container_summary==Disks RG-14-010_001-005;;physical_details==audio recordings`

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
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Linked Agent Archival Record Relators
        - role
            - - ArchivesSpace field equivalent: Role
            - Required in field: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Linked Agent Role
    - Example: `role==creator;;relator==pht;;ref==/agents/corporate_entities/388`

### Columns related to `Subjects`

??? note "subjects"
    - ArchivesSpace field equivalent: Subjects section
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Ref](../workflow/2-fill-out-templates.md/#ref)
    - Example: `/subjects/2553|/subjects/551`

### Columns related to `Notes`

??? note "notes"
    - ArchivesSpace field equivalent: Notes
    - Required in CSV: :x: False
    - Allows multiple values: :white_check_mark: True
    - Data type: [Subfield type](../workflow/2-fill-out-templates.md/#subfield-type)
    - Allowed subfields:
        - type
            - ArchivesSpace field equivalent: Note Type
            - Required in CSV: :white_check_mark: True
            - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Note Digital Object Type
        - content
            - ArchivesSpace field equivalent:  Content
            - Required in CSV: :white_check_mark: True
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - publish
            - ArchivesSpace field equivalent: Publish?
            - Required in CSV: :x: False
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
    - Example: `type==summary;;content==Johns Hopkins University television programs collection; Coll-0008_010; Files in this bag are all from the Tomorrow show, ranging in file names A5968-A5992. 9 files; MP4 file format. Coll-0008_001 is on VSM. Coll-0008-002-010 are in APTrust.;;publish==FALSE`


## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postDigitalObjects.py` script.

- `'jsonmodel_type': 'digital_object'`
- `'is_slug_auto': False`
