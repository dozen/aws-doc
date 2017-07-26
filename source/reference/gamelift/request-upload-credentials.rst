[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift request-upload-credentials:


**************************
request-upload-credentials
**************************



===========
Description
===========



Retrieves a fresh set of upload credentials and the assigned Amazon S3 storage location for a specific build. Valid credentials are required to upload your game build files to Amazon S3.

 

.. warning::

  

  Call this action only if you need credentials for a build created with  create-build . This is a rare situation; in most cases, builds are created using the CLI command ``upload-build`` , which creates a build record and also uploads build files. 

  

 

Upload credentials are returned when you create the build, but they have a limited lifespan. You can get fresh credentials and use them to re-upload game files until the state of that build changes to READY. Once this happens, you must create a brand new build.



========
Synopsis
========

::

    request-upload-credentials
  --build-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--build-id`` (string)


  Unique identifier for the build you want to get credentials for. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

UploadCredentials -> (structure)

  

  AWS credentials required when uploading a game build to the storage location. These credentials have a limited lifespan and are valid only for the build they were issued for.

  

  AccessKeyId -> (string)

    

    Access key for an AWS account.

    

    

  SecretAccessKey -> (string)

    

    Secret key for an AWS account.

    

    

  SessionToken -> (string)

    

    Token specific to a build ID.

    

    

  

StorageLocation -> (structure)

  

  Amazon S3 path and key, identifying where the game build files are stored.

  

  Bucket -> (string)

    

    Amazon S3 bucket identifier.

    

    

  Key -> (string)

    

    Amazon S3 bucket key.

    

    

  

