[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot deprecate-thing-type:


********************
deprecate-thing-type
********************



===========
Description
===========



Deprecates a thing type. You can not associate new things with deprecated thing type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DeprecateThingType>`_


========
Synopsis
========

::

    deprecate-thing-type
  --thing-type-name <value>
  [--undo-deprecate | --no-undo-deprecate]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-type-name`` (string)


  The name of the thing type to deprecate.

  

``--undo-deprecate`` | ``--no-undo-deprecate`` (boolean)


  Whether to undeprecate a deprecated thing type. If **true** , the thing type will not be deprecated anymore and you can associate it with things.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

