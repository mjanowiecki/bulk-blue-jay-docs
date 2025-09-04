---
title: Post new agents to ArchivesSpace
hide:
  - toc
---

# Post new agents to ArchivesSpace

Once you have completed the processing of your collection and have filled out the needed CSV templates, you should be ready to start uploading new agents and new subjects to ArchivesSpace. 

!!! Tip
    The order you upload agents, top containers, and subjects does not matter, but it is important to upload all new entities before your archival and digital objects.

!!! Tip
    For help running scripts, please see [Create entity scripts](../python-scripts/running-the-scripts.md) help page.
    

For each type of agent (corporate entities and persons) in your new collection, complete the following steps.

## :material-tie: Corporate Entities
1. Get list of the corporate entities currently in your ArchivesSpace production instance by running [getAllCorporateEntitiesCSV.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/get-existing-entities/getAllCorporateEntitiesCSV.py) script to create `allCorporateEntities.csv`. The time it takes to run the script will vary based on the number of entities and your internet speed, but in general, allow at least 5 minutes per 1000 entities for GET scripts.

2. Use `allCorporateEntities.csv` to determine if any of the corporate entities in your completed `corporate-entity-template.csv` already exist in ArchivesSpace. While you can use any method you are comfortable with to determine if any corporate entities already exist, I would recommend running `mergeTwoCSVs.py` to automatically match existing corporate entities by name. For more instructions on this method, see [matching workflow](../python-scripts/matching-names.md).

3. If any corporate entities already exist, delete their rows from `corporate-entity-template.csv` and add their names and URIs to `alreadyExistingEntities.csv`. This should leave you with a `corporate-entity-template.csv` that only contains new corporate entities.

4. Use [postCorporateAgents.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/create-entities/postCorporateAgents.py) to post the corporate entities remaining in `corporate-entity-template.csv` to ArchivesSpace.

## :fontawesome-solid-user: Persons
1. Get list of the persons currently in your ArchivesSpace production instance by running [getAllPersonsCSV.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/get-existing-entities/getAllPersonsCSV.py) to create `allPersons.csv`. The time it takes to run the script will vary based on the number of entities and your internet speed, but in general, allow at least 5 minutes per 1000 entities for GET scripts.

2. Use `allPersons.csv` to determine if any of the persons in your completed `person-template.csv` already exist in ArchivesSpace. While you can use any method you are comfortable with to determine if any persons already exist, I would recommend running `mergeTwoCSVs.py` to automatically match existing persons by name. For more instructions on this method, see [matching workflow](../python-scripts/matching-names.md).

3. If any persons already exist, delete their rows from `person-template.csv` and add their names and URIs to `alreadyExistingEntities.csv`. This should leave you with a `person-template.csv` that only contains new persons.

4. Use [postPeopleAgents.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/create-entities/postPeopleAgents.py) to post the persons remaining in `person-template.csv` to ArchivesSpace.

## :fontawesome-solid-user-group: Families
1. Get list of the persons currently in your ArchivesSpace production instance by running [getAllFamiliesCSV.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/get-existing-entities/getAllFamiliesCSV.py) to create `allFamilies.csv`.The time it takes to run the script will vary based on the number of entities and your internet speed, but in general, allow at least 5 minutes per 1000 entities for GET scripts.

2. Use `allFamilies.csv` to determine if any of the persons in your completed `family-template.csv` already exist in ArchivesSpace. While you can use any method you are comfortable with to determine if any persons already exist, I would recommend running `mergeTwoCSVs.py` to automatically match existing Families by name. For more instructions on this method, see [matching workflow](../python-scripts/matching-names.md).

3. If any families already exist, delete their rows from `family-template.csv` and add their names and URIs to `alreadyExistingEntities.csv`. This should leave you with a `family-template.csv` that only contains new families.

4. Use [postFamilyAgents.py](https://github.com/mjanowiecki/archivesspace-collection-ingest/blob/main/create-entities/postFamilyAgents.py) to post the families remaining in `family-template.csv` to ArchivesSpace.
