[ :ref:`aws <cli:aws>` . :ref:`codebuild <cli:aws codebuild>` ]

.. _cli:aws codebuild list-projects:


*************
list-projects
*************



===========
Description
===========



Gets a list of build project names, with each build project name representing a single build project.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codebuild-2016-10-06/ListProjects>`_


========
Synopsis
========

::

    list-projects
  [--sort-by <value>]
  [--sort-order <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--sort-by`` (string)


  The criterion to be used to list build project names. Valid values include:

   

   
  * ``CREATED_TIME`` : List the build project names based on when each build project was created. 
   
  * ``LAST_MODIFIED_TIME`` : List the build project names based on when information about each build project was last changed. 
   
  * ``NAME`` : List the build project names based on each build project's name. 
   

   

  Use ``sortOrder`` to specify in what order to list the build project names based on the preceding criteria.

  

  Possible values:

  
  *   ``NAME``

  
  *   ``CREATED_TIME``

  
  *   ``LAST_MODIFIED_TIME``

  

  

``--sort-order`` (string)


  The order in which to list build projects. Valid values include:

   

   
  * ``ASCENDING`` : List the build project names in ascending order. 
   
  * ``DESCENDING`` : List the build project names in descending order. 
   

   

  Use ``sortBy`` to specify the criterion to be used to list build project names.

  

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

nextToken -> (string)

  

  If there are more than 100 items in the list, only the first 100 items are returned, along with a unique string called a *next token* . To get the next batch of items in the list, call this operation again, adding the next token to the call.

  

  

projects -> (list)

  

  The list of build project names, with each build project name representing a single build project.

  

  (string)

    

    

  

