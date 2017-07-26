[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar list-projects:


*************
list-projects
*************



===========
Description
===========



Lists all projects in AWS CodeStar associated with your AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/ListProjects>`_


========
Synopsis
========

::

    list-projects
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  The continuation token to be used to return the next set of results, if the results cannot be returned in one response.

  

``--max-results`` (integer)


  The maximum amount of data that can be contained in a single set of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

projects -> (list)

  

  A list of projects.

  

  (structure)

    

    Information about the metadata for a project.

    

    projectId -> (string)

      

      The ID of the project.

      

      

    projectArn -> (string)

      

      The Amazon Resource Name (ARN) of the project.

      

      

    

  

nextToken -> (string)

  

  The continuation token to use when requesting the next set of results, if there are more results to be returned.

  

  

