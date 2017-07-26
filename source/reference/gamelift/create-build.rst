[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-build:


************
create-build
************



===========
Description
===========



Creates a new Amazon GameLift build from a set of game server binary files stored in an Amazon Simple Storage Service (Amazon S3) location. To use this API call, create a ``.zip`` file containing all of the files for the build and store it in an Amazon S3 bucket under your AWS account. For help on packaging your build files and creating a build, see `Uploading Your Game to Amazon GameLift <http://docs.aws.amazon.com/gamelift/latest/developerguide/gamelift-build-intro.html>`_ .

 

.. warning::

   

  Use this API action ONLY if you are storing your game build files in an Amazon S3 bucket. To create a build using files stored locally, use the CLI command ` ``upload-build`` http://docs.aws.amazon.com/cli/latest/reference/gamelift/upload-build.html`_ , which uploads the build files from a file location you specify.

   

 

To create a new build using ``create-build`` , identify the storage location and operating system of your game build. You also have the option of specifying a build name and version. If successful, this action creates a new build record with an unique build ID and in ``INITIALIZED`` status. Use the API call  describe-build to check the status of your build. A build must be in ``READY`` status before it can be used to create fleets to host your game.

 

Build-related operations include:

 

 
*  create-build   
 
*  list-builds   
 
*  describe-build   
 
*  update-build   
 
*  delete-build   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/CreateBuild>`_


========
Synopsis
========

::

    create-build
  [--name <value>]
  [--storage-location <value>]
  [--operating-system <value>]
  [--build-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Descriptive label that is associated with a build. Build names do not need to be unique. You can use  update-build to change this value later. 

  

``--storage-location`` (structure)


  Amazon S3 location of the game build files to be uploaded. The S3 bucket must be owned by the same AWS account that you're using to manage Amazon GameLift. It also must in the same region that you want to create a new build in. Before calling ``create-build`` with this location, you must allow Amazon GameLift to access your Amazon S3 bucket (see `Create a Build with Files in Amazon S3 <http://docs.aws.amazon.com/gamelift/latest/developerguide/gamelift-build-cli-uploading.html#gamelift-build-cli-uploading-create-build>`_ ).

  



Shorthand Syntax::

    Bucket=string,Key=string,RoleArn=string




JSON Syntax::

  {
    "Bucket": "string",
    "Key": "string",
    "RoleArn": "string"
  }



``--operating-system`` (string)


  Operating system that the game server binaries are built to run on. This value determines the type of fleet resources that you can use for this build. If your game build contains multiple executables, they all must run on the same operating system.

  

  Possible values:

  
  *   ``WINDOWS_2012``

  
  *   ``AMAZON_LINUX``

  

  

``--build-version`` (string)


  Version that is associated with this build. Version strings do not need to be unique. You can use  update-build to change this value later. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Build -> (structure)

  

  The newly created build record, including a unique build ID and status. 

  

  BuildId -> (string)

    

    Unique identifier for a build.

    

    

  Name -> (string)

    

    Descriptive label that is associated with a build. Build names do not need to be unique. It can be set using  create-build or  update-build .

    

    

  Version -> (string)

    

    Version that is associated with this build. Version strings do not need to be unique. This value can be set using  create-build or  update-build .

    

    

  Status -> (string)

    

    Current status of the build.

     

    Possible build statuses include the following:

     

     
    * **INITIALIZED** – A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this status. When a build is successfully created, the build status is set to this value.  
     
    * **READY** – The game build has been successfully uploaded. You can now create new fleets for this build. 
     
    * **FAILED** – The game build upload failed. You cannot create new fleets for this build.  
     

    

    

  SizeOnDisk -> (long)

    

    File size of the uploaded game build, expressed in bytes. When the build status is ``INITIALIZED`` , this value is 0.

    

    

  OperatingSystem -> (string)

    

    Operating system that the game server binaries are built to run on. This value determines the type of fleet resources that you can use for this build.

    

    

  CreationTime -> (timestamp)

    

    Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  

UploadCredentials -> (structure)

  

  This element is not currently in use.

  

  AccessKeyId -> (string)

    

    Access key for an AWS account.

    

    

  SecretAccessKey -> (string)

    

    Secret key for an AWS account.

    

    

  SessionToken -> (string)

    

    Token specific to a build ID.

    

    

  

StorageLocation -> (structure)

  

  Amazon S3 location specified in the request.

  

  Bucket -> (string)

    

    Amazon S3 bucket identifier. This is the name of your S3 bucket.

    

    

  Key -> (string)

    

    Name of the zip file containing your build files. 

    

    

  RoleArn -> (string)

    

    Amazon Resource Name (`ARN <http://docs.aws.amazon.com/AmazonS3/latest/dev/s3-arn-format.html>`_ ) for the access role that allows Amazon GameLift to access your S3 bucket.

    

    

  



.. _http://docs.aws.amazon.com/cli/latest/reference/gamelift/upload-build.html: http://docs.aws.amazon.com/cli/latest/reference/gamelift/upload-build.html
