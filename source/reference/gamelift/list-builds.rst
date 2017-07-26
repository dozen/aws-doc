[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift list-builds:


***********
list-builds
***********



===========
Description
===========



Retrieves build records for all builds associated with the AWS account in use. You can limit results to builds that are in a specific status by using the ``Status`` parameter. Use the pagination parameters to retrieve results in a set of sequential pages. 

 

.. note::

   

  Build records are not listed in any particular order.

   

 

Build-related operations include:

 

 
*  create-build   
 
*  list-builds   
 
*  describe-build   
 
*  update-build   
 
*  delete-build   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/ListBuilds>`_


========
Synopsis
========

::

    list-builds
  [--status <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--status`` (string)


  Build status to filter results by. To retrieve all builds, leave this parameter empty.

   

  Possible build statuses include the following:

   

   
  * **INITIALIZED** – A new build has been defined, but no files have been uploaded. You cannot create fleets for builds that are in this status. When a build is successfully created, the build status is set to this value.  
   
  * **READY** – The game build has been successfully uploaded. You can now create new fleets for this build. 
   
  * **FAILED** – The game build upload failed. You cannot create new fleets for this build.  
   

  

  Possible values:

  
  *   ``INITIALIZED``

  
  *   ``READY``

  
  *   ``FAILED``

  

  

``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Builds -> (list)

  

  Collection of build records that match the request.

  

  (structure)

    

    Properties describing a game build.

     

    Build-related operations include:

     

     
    *  create-build   
     
    *  list-builds   
     
    *  describe-build   
     
    *  update-build   
     
    *  delete-build   
     

    

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

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

