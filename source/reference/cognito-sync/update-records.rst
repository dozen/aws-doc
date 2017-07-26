[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync update-records:


**************
update-records
**************



===========
Description
===========



Posts updates to records and adds and deletes records for a dataset and user.

 

The sync count in the record patch is your last known sync count for that record. The server will reject an update-records request with a ResourceConflictException if you try to patch a record with a new value but a stale sync count.

 

For example, if the sync count on the server is 5 for a key called highScore and you try and submit a new highScore with sync count of 4, the request will be rejected. To obtain the current sync count for a record, call ListRecords. On a successful update of the record, the response returns the new sync count for that record. You should present that sync count the next time you try to update that same record. When the record does not exist, specify the sync count as 0.

 

This API can be called with temporary user credentials provided by Cognito Identity or with developer credentials.



========
Synopsis
========

::

    update-records
  --identity-pool-id <value>
  --identity-id <value>
  --dataset-name <value>
  [--device-id <value>]
  [--record-patches <value>]
  --sync-session-token <value>
  [--client-context <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--identity-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--dataset-name`` (string)
A string of up to 128 characters. Allowed characters are a-z, A-Z, 0-9, '_' (underscore), '-' (dash), and '.' (dot).

``--device-id`` (string)


  The unique ID generated for this device by Cognito.

  

``--record-patches`` (list)
A list of patch operations.



Shorthand Syntax::

    Op=string,Key=string,Value=string,SyncCount=long,DeviceLastModifiedDate=timestamp ...




JSON Syntax::

  [
    {
      "Op": "replace"|"remove",
      "Key": "string",
      "Value": "string",
      "SyncCount": long,
      "DeviceLastModifiedDate": timestamp
    }
    ...
  ]



``--sync-session-token`` (string)
The sync-session-token returned by a previous call to list-records for this dataset and identity.

``--client-context`` (string)
Intended to supply a device ID that will populate the lastModifiedBy field referenced in other methods. The client-context field is not yet implemented.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Records -> (list)

  A list of records that have been updated.

  (structure)

    The basic data structure of a dataset.

    Key -> (string)

      The key for the record.

      

    Value -> (string)

      The value for the record.

      

    SyncCount -> (long)

      The server sync count for this record.

      

    LastModifiedDate -> (timestamp)

      The date on which the record was last modified.

      

    LastModifiedBy -> (string)

      The user/device that made the last change to this record.

      

    DeviceLastModifiedDate -> (timestamp)

      The last modified date of the client device.

      

    

  

