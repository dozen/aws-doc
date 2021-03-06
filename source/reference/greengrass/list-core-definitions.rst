[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass list-core-definitions:


*********************
list-core-definitions
*********************



===========
Description
===========

Retrieves a list of core definitions.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/ListCoreDefinitions>`_


========
Synopsis
========

::

    list-core-definitions
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-results`` (string)
Specifies the maximum number of list results to be returned in this page

``--next-token`` (string)
Specifies the pagination token used when iterating through a paginated request

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Definitions -> (list)

  Definitions

  (structure)

    Information on the Definition

    Arn -> (string)

      Arn of the definition.

      

    CreationTimestamp -> (string)

      Timestamp of when the definition was created.

      

    Id -> (string)

      Id of the definition.

      

    LastUpdatedTimestamp -> (string)

      Last updated timestamp of the definition.

      

    LatestVersion -> (string)

      Last version of the definition.

      

    LatestVersionArn -> (string)

      Latest version arn of the definition.

      

    Name -> (string)

      Name of the definition.

      

    

  

NextToken -> (string)

  The token for the next set of results, or ''null'' if there are no additional results.

  

