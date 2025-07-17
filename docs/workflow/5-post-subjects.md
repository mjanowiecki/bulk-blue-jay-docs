---
title: Post new subjects to ArchivesSpace
---

# Post new subjects to ArchivesSpace

!!! Tip
    The order you upload agents, top containers, and subjects does not matter, but it is important to upload all new entities before your archival objects.

!!! Tip
    For help running scripts, please see [Create entity scripts](../python-scripts/running-the-scripts.md) help page.

## Steps
1. Get a list of the subjects currently in your ArchivesSpace production instance by running [getAllSubjectsCSV.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/get-existing-entities/getSubjectsCSV.py) script to create `allSubjects.csv`. The time it takes to run the script will vary based on the number of entities and your internet speed, but in general, allow at least 5 minutes per 1000 entities for GET scripts.

2. Use `allSubjects.csv` to determine if any of the subjects in your completed `subject-template.csv` already exist in ArchivesSpace. While you can use any method you are comfortable with to determine if any subjects already exist, I would recommend running [mergeTwoCSVs.py]() to automatically match existing subjects by name. For more instructions on this method, see [matching workflow](../python-scripts/matching-names.md).

3. If any subjects already exist, delete their rows from `subject-template.csv` and add their names and URIs to `alreadyExistingEntities.csv`. This should leave you with a `subject-template.csv` that only contains new subjects.

4. Use [postSubjects.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/create-entities/postSubjects.py) to post the subjects remaining in `subject-template.csv` to ArchivesSpace.
