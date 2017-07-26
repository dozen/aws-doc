[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-build:


**************
describe-build
**************



===========
Description
===========



Retrieves properties for a build. To get a build record, specify a build ID. If successful, an object containing the build properties is returned.



========
Synopsis
========

::

    describe-build
  --build-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--build-id`` (string)


  Unique identifier for the build you want to retrieve properties for. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Build -> (structure)

  

  Set of properties describing the requested build.

  

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

    

    

  

