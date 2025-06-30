---
title: Set up workflow
---

# Set up workflow

To use this workflow, there are a few details to configure on your local machine.

## 1. Clone repository from GitHub

To fully run this workflow, you must be able to run the Python scripts contained [archivesspace-collection-ingest](https://github.com/mjanowiecki/archivesspace-collection-ingest) from your local computer. The easiest way to do this is by cloning [archivesspace-collection-ingest](https://github.com/mjanowiecki/archivesspace-collection-ingest). 

For more instructions on cloning, see [:simple-github: GitHub Docs: Cloning a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).

## 2. Export `enumerations.csv`

Some of the fields in ArchivesSpace objects only accept values from controlled lists. In the staff interface of ArchivesSpace, these controlled lists are found at `System → Controlled Value lists`. 

In order to reduce typos and errors in our objects, our scripts verify many of these values against the export of these lists which is found by clicking `Download CSV` on the Controlled Value list page. Therefore, in order to run these scripts you must:

1. Download Controlled Value list CSV from your ArchivesSpace instance. 
2. Rename the CSV `enumerations.csv`. 
3. Place the CSV in the directory in the `create_entities` folder of your archivesspace-collection-ingest repository.

If your controlled lists are ever updated in ArchivesSpace, simply replace the CSV with a newer export and rename it as `enumerations.csv`. You do not have to make any changes to the CSV data itself.

## 3. Create `secret` files

To run these scripts against your ArchivesSpace API, you must have two `secret` files in both the `create_entities` and `get-existing-entities` folders with your scripts. These files are `secret.py` and `secretProd.py`. Each will have the following five variables, one for your development/test instance of ArchivesSpace and one for your production site.

!!! warning
    Be sure to add these scripts to your `.gitignore` file in order to avoid uploading your password to a public repository like [GitHub](https://github.com/).

```py title="secret.py"
baseURL = 'yourarchivesspace.com'
user = 'username'
password = 'password'
repository = '4'
verify = False
```
