[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes tags for a WorkSpace.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/DescribeTags>`_


========
Synopsis
========

::

    describe-tags
  --resource-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-id`` (string)


  The resource ID of the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TagList -> (list)

  

  The list of tags.

  

  (structure)

    

    Describes the tag of the WorkSpace.

    

    Key -> (string)

      

      The key of the tag.

      

      

    Value -> (string)

      

      The value of the tag.

      

      

    

  

