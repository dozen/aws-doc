[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-associated-role:


*******************
get-associated-role
*******************



===========
Description
===========

Retrieves the role associated with a particular group.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetAssociatedRole>`_


========
Synopsis
========

::

    get-associated-role
  --group-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AssociatedAt -> (string)

  Time when the role was associated for the group.

  

RoleArn -> (string)

  Arn of the role that is associated with the group.

  

