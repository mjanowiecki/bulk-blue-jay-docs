---
title: How to fill out digital object template CSV
hide:
  - toc
---
# How to fill out digital object template CSV

## :octicons-light-bulb-16: Example of completed `digital_objects.csv`

*Coming soon!*

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

??? note "digital_object_type"
    - ArchivesSpace field equivalent: Digital Object Type
    - Required in CSV: :x: False
    - Allows multiple values: :x: False
    - Data type: [Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Digital Object Digital Object Type

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
            - Data type:[Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Date Label
        - expression
            - ArchivesSpace field equivalent: Expression
            - Required in field: :x: False
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - date_type
            - ArchivesSpace field equivalent: Type
            - Required in field: :white_check_mark: True
            - Data type:[Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Date Type
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
            - Data type:[Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Date Certainty
    - Example: `label==creation;;expression==2000-2010;;date_type==inclusive;;begin==2000;;end==2010`

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
            - ArchivesSpace field equivalent: 
            - Required in CSV:
            - Data type:
    - Example: `file_uri==http://jhir.library.jhu.edu/handle/1774.2/63642;;publish==TRUE;;is_represenative==FALSE`

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
            - Data type:[Controlled list](../workflow/2-fill-out-templates.md/#controlled-list) - Note Digital Object Type
        - content
            - ArchivesSpace field equivalent:  Content
            - Required in CSV: :white_check_mark: True
            - Data type: [String](../workflow/2-fill-out-templates.md/#string)
        - publish
            - ArchivesSpace field equivalent: Publish?
            - Required in CSV: :x: False
            - Data type: [Boolean](../workflow/2-fill-out-templates.md/#boolean)
    - Example: `type==note;;content==Johns Hopkins University television programs collection; Coll-0008_010; Files in this bag are all from the Tomorrow show, ranging in file names A5968-A5992. 9 files; MP4 file format. Coll-0008_001 is on VSM. Coll-0008-002-010 are in APTrust.;;publish==FALSE`


## :octicons-lock-16: Default values

These are values automatically added to each record and can only be changed by editing the `postDigitalObjects.py` script.

- `'jsonmodel_type': 'digital_object'`
- `'suppressed': false'`
- 
