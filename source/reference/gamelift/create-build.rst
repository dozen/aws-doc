[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-build:


************
create-build
************



===========
Description
===========



Initializes a new build record and generates information required to upload a game build to Amazon GameLift. Once the build record has been created and is in an INITIALIZED state, you can upload your game build.

 

.. warning::

  

  To create a build, use the CLI command ``upload-build`` , which creates a new build record and uploads the build files in one step. (See the `Amazon GameLift Developer Guide`_ for more details on the CLI and the upload process.) Call the ``create-build`` action only if you have your own Amazon Simple Storage Service (Amazon S3) client and need to manually upload your build files.

  

 

To create a new build, optionally specify a build name and version. This metadata is stored with other properties in the build record and is displayed in the GameLift console (but not visible to players). If successful, this action returns the newly created build record along with an Amazon S3 storage location and AWS account credentials. Use the location and credentials to upload your game build.



========
Synopsis
========

::

    create-build
  [--name <value>]
  [--build-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  Descriptive label associated with this build. Build names do not need to be unique. A build name can be changed later using  update-build .

  

``--build-version`` (string)


  Version associated with this build. Version strings do not need to be unique to a build. A build version can be changed later using  update-build .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Build -> (structure)

  

  Set of properties for the newly created build.

  

  BuildId -> (string)

    

    Unique identifier for a build.

    

    

  Name -> (string)

    

    Descriptive label associated with this build. Build names do not need to be unique. It can be set using  create-build or  update-build .

    

    

  Version -> (string)

    

    Version associated with this build. Version strings do not need to be unique to a build. This value can be set using  create-build or  update-build .

    

    

  Status -> (string)

    

    Current status of the build. Possible build states include: 

    
    * INITIALIZED: A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this state. When a build is successfully created, the build state is set to this value. 
    
    * READY: The game build has been successfully uploaded. You can now create new fleets for this build.
    
    * FAILED: The game build upload failed. You cannot create new fleets for this build. 
    

    

    

    

  SizeOnDisk -> (long)

    

    File size of the uploaded game build, expressed in bytes. When the build state is INITIALIZED, this value is 0.

    

    

  CreationTime -> (timestamp)

    

    Time stamp indicating when this object was created. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

    

    

  

UploadCredentials -> (structure)

  

  AWS credentials required when uploading a game build to the storage location. These credentials have a limited lifespan and are valid only for the build they were issued for. If you need to get fresh credentials, call  request-upload-credentials .

  

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

    

    

  



.. _Amazon GameLift Developer Guide: http://docs.aws.amazon.com/gamelift/latest/developerguide/
