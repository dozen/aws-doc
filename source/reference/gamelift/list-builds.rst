[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift list-builds:


***********
list-builds
***********



===========
Description
===========



Retrieves build records for all builds associated with an AWS account. You can filter the result set by build status. Use the pagination parameters to retrieve results in a set of sequential pages. 

 

.. note::

  

  Build records are not listed in any particular order.

  



========
Synopsis
========

::

    list-builds
  [--status <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--status`` (string)


  Build state to filter results on. Use this parameter to retrieve builds in a certain state. To retrieve all builds, leave this parameter empty. Possible build states include: 

  
  * INITIALIZED: A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this state. When a build is successfully created, the build state is set to this value. 
  
  * READY: The game build has been successfully uploaded. You can now create new fleets for this build.
  
  * FAILED: The game build upload failed. You cannot create new fleets for this build. 
  

  

  

  Possible values:

  
  *   ``INITIALIZED``

  
  *   ``READY``

  
  *   ``FAILED``

  

  

``--limit`` (integer)


  Maximum number of results to return. You can use this parameter with *NextToken* to get results as a set of sequential pages.

  

``--next-token`` (string)


  Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Builds -> (list)

  

  Collection of build records that match the request. 

  

  (structure)

    

    Properties describing a game build.

    

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

      

      

    

  

NextToken -> (string)

  

  Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

   

  .. note::

    

    If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

    

  

  

