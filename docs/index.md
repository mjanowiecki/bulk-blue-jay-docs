---
title: Bulk Blue Jay Workflow
hide:
  - toc
---
# Bulk Blue Jay Workflow

The Bulk Blue Jay Workflow (BBJW) is workflow via Python scripts to ingest full collections via [ArchivesSpace REST API](https://archivesspace.github.io/archivesspace/api/#archivesspace-rest-api).

## Background of project

This workflow was developed at the [Johns Hopkins University Sheridan Libraries](https://www.library.jhu.edu/) in 2022-2023 as a solution to the problem of how to ingest file-level metadata into the collection finding aid in ArchivesSpace from a spreadsheet with over 55,000 rows of complex metadata. The workflow contains a set of CSV templates for archival objects, digital objects, top containers, subjects, agent records of each type, plus a corresponding set of Python scripts and instructions for uploading and correctly linking the metadata contained in those CSV spreadsheets via the ArchivesSpace API.

We developed this workflow for the [Barbara A. Mikulski papers](https://archivesspace.library.jhu.edu/repositories/3/resources/1485), a congressional collection that documents the political career of Senator Barbara Mikulski. At 1093 boxes and over 55,000 folders, the Mikulski papers are the largest manuscript collection at our institution. The collection finding aid contains file-level metadata on access restrictions, agents, subjects, and container, all necessary for this archival processing project and made possible at this large scale via this workflow.

## What this project does

This project uses CSV spreadsheets and Python scripts to upload entities (like Subjects, Archival Objects, etc.) associated with a collection to ArchivesSpace via REST API.

## Our team

<div class="grid cards" markdown>

-   **:simple-bookstack: [Jenelle Clark](https://www.library.jhu.edu/staff/jenelle-clark/)**

    ---
 
    *Accessioning Archivist*

    *Johns Hopkins Sheridan Libraries*

-   **:material-book-search: [Kristen Diehl](https://www.library.jhu.edu/staff/kristen-diehl/)**

    ---
    
    *Processing Archivist*

    *Johns Hopkins Sheridan Libraries*


- **:octicons-tag-16: [Michelle Janowiecki](https://www.library.jhu.edu/staff/michelle-janowiecki/)**

    ---

    *Metadata Librarian*
    
    *Johns Hopkins Sheridan Libraries*

</div>

## A note on examples

Throughout this documentation, the Blue Jay Example Collection is used to help explain our workflow in greater detail. This collection is entirely fictitious and does not represent best archival practices. Instead, the examples were formulated for their ability to clarify data entry and workflows, rather adherence to best practices in DACS or other descriptive practices.

## Copyright

This documentation is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](https://creativecommons.org/licenses/by-nc/4.0/).


## Additional resources
 - [ArchivesSpace RESTful API](https://archivesspace.github.io/archivesspace/api/#introduction)
 - [ArchivesSpace Working with the API](https://docs.archivesspace.org/api/)
 - [ArchivesSpace Schema List](https://archivesspace.github.io/archivesspace/doc/)
