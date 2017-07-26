[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift request-upload-credentials:


**************************
request-upload-credentials
**************************



===========
Description
===========



 *This API call is not currently in use.* Retrieves a fresh set of upload credentials and the assigned Amazon S3 storage location for a specific build. Valid credentials are required to upload your game build files to Amazon S3.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/RequestUploadCredentials>`_


========
Synopsis
========

::

    request-upload-credentials
  --build-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--build-id`` (string)


  Unique identifier for a build to get credentials for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    Amazon S3 bucket identifier. This is the name of your S3 bucket.

    

    

  Key -> (string)

    

    Name of the zip file containing your build files. 

    

    

  RoleArn -> (string)

    

    Amazon Resource Name (`ARN <http://docs.aws.amazon.com/AmazonS3/latest/dev/s3-arn-format.html>`_ ) for the access role that allows Amazon GameLift to access your S3 bucket.

    

    

  

