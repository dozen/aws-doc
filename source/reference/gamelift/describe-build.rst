[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-build:


**************
describe-build
**************



===========
Description
===========



Retrieves properties for a build. To get a build record, specify a build ID. If successful, an object containing the build properties is returned.

 

Build-related operations include:

 

 
*  create-build   
 
*  list-builds   
 
*  describe-build   
 
*  update-build   
 
*  delete-build   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeBuild>`_


========
Synopsis
========

::

    describe-build
  --build-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--build-id`` (string)


  Unique identifier for a build to retrieve properties for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Build -> (structure)

  

  Set of properties describing the requested build.

  

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

    

    

  

