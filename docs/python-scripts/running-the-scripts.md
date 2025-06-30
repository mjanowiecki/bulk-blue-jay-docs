# How to run scripts

## The basics
Before running any scripts, ensure you have the following in the same folder:

- [x] the script
- [x] `secret.py`
- [x] `secretProd.py`
- [x] the relevant csv

If relevant, also ensure you are on your institution's VPN.

!!! Tip
    Double check that you have write access to both the sandbox and production instances of ArchivesSpace.

## Using the command line/terminal

!!! Tip
    Always `cd` into the folder with your script before running.

These scripts, one for each type of ArchivesSpace entity, take data from a CSV and create valid JSON records. Then, the script will either `POST` these JSON records to the relevant ArchivesSpace endpoint or save the JSON records to your local filesystem. We use the `argparse` module to input our decision in the terminal. We also use the `argparse` module to tell the script what our CSV file is named. The CSV file in this example is located in the same folder as our script. 

So, if we would like to `POST` our JSON records to ArchivesSpace and our CSV is called `collection-10-people.csv`, the terminal command would look something like this:

```
python postPeopleAgents.py -file collection-10-people.csv -postRecord True
```

Alternatively, if we don't want to post the JSON records to ArchivesSpace, our input in the terminal might look like this:

```
python postPeopleAgents.py -f collection-10-people.csv -p False
```

If you input `True` to `-postRecord`, the terminal will then prompt you to enter the secret filename for the Production instance of ArchivesSpace. 

```
python postPeopleAgents.py -f collection-10-people.csv -p True
To edit production server, enter secret filename: 
```

To `POST` to your Production instance of ArchivesSpace, type `secretProd` and hit enter. 
```
python postPeopleAgents.py -f collection-10-people.csv -p True
To edit production server, enter secret filename: secretProd
Editing Production
```

If you input anything else other than `secretProd`, the script automatically connects to the development/test instance of your ArchivesSpace site instead. You can also connect to development/test instance of your ArchivesSpace site by hitting enter without typing anything when the prompt appears.
```
python postPeopleAgents.py -f collection-10-people.csv -p True
To edit production server, enter secret filename:
Editing Stage
```

## Errors

### JSONDecodeError

`requests.exceptions.JSONDecodeError: Expecting value: line 1 colummn 1 (char 0)`

This error typically happens when the API returns an error code instead of a JSON record, most frequently when your login fails or if the API cannot find locate the resource requested. Occasionally, this will also occur when trying to post a new entity when your server is out of memory. To see a more specific error code, delete the trailing `.json()` from the relevant request line, add a line below printing the output (for instance, `print(auth)` or `print(output)`) and rerun the script.

Meaning of common error codes:

- `400: Bad Request` -- Your request is invalid. Check that your URL is formatted properly.
- `401: Unauthorized` -- Something bad is happening with your login.
- `403: Forbidden` -- You don't have permissions for this request.
- `404: Not Found` -- The specified entity could not be found. This is typically an improperly formatted URL.
- `500: Internal Server Error` -- Typically, this is not your fault! Talk to your tech folks. Mostly likely your server is out of memory.
- `503: Service Unavailable` --  Typically, this is not your fault! Talk to your tech folks.
