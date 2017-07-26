[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar list-resources:


**************
list-resources
**************



===========
Description
===========



Lists resources associated with a project in AWS CodeStar.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/ListResources>`_


========
Synopsis
========

::

    list-resources
  --project-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--project-id`` (string)


  The ID of the project.

  

``--next-token`` (string)


  The continuation token for the next set of results, if the results cannot be returned in one response.

  

``--max-results`` (integer)


  he maximum amount of data that can be contained in a single set of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

resources -> (list)

  

  An array of resources associated with the project. 

  

  (structure)

    

    Information about a resource for a project.

    

    id -> (string)

      

      The Amazon Resource Name (ARN) of the resource.

      

      

    

  

nextToken -> (string)

  

  The continuation token to use when requesting the next set of results, if there are more results to be returned.

  

  

