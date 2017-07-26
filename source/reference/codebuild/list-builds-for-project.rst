[ :ref:`aws <cli:aws>` . :ref:`codebuild <cli:aws codebuild>` ]

.. _cli:aws codebuild list-builds-for-project:


***********************
list-builds-for-project
***********************



===========
Description
===========



Gets a list of build IDs for the specified build project, with each build ID representing a single build.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codebuild-2016-10-06/ListBuildsForProject>`_


========
Synopsis
========

::

    list-builds-for-project
  --project-name <value>
  [--sort-order <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--project-name`` (string)


  The name of the build project.

  

``--sort-order`` (string)


  The order to list build IDs. Valid values include:

   

   
  * ``ASCENDING`` : List the build IDs in ascending order by build ID. 
   
  * ``DESCENDING`` : List the build IDs in descending order by build ID. 
   

  

  Possible values:

  
  *   ``ASCENDING``

  
  *   ``DESCENDING``

  

  

``--next-token`` (string)


  During a previous call, if there are more than 100 items in the list, only the first 100 items are returned, along with a unique string called a *next token* . To get the next batch of items in the list, call this operation again, adding the next token to the call. To get all of the items in the list, keep calling this operation with each subsequent next token that is returned, until no more next tokens are returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ids -> (list)

  

  A list of build IDs for the specified build project, with each build ID representing a single build.

  

  (string)

    

    

  

nextToken -> (string)

  

  If there are more than 100 items in the list, only the first 100 items are returned, along with a unique string called a *next token* . To get the next batch of items in the list, call this operation again, adding the next token to the call.

  

  

