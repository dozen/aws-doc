[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot delete-thing-type:


*****************
delete-thing-type
*****************



===========
Description
===========



Deletes the specified thing type . You cannot delete a thing type if it has things associated with it. To delete a thing type, first mark it as deprecated by calling  deprecate-thing-type , then remove any associated things by calling  update-thing to change the thing type on any associated thing, and finally use  delete-thing-type to delete the thing type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DeleteThingType>`_


========
Synopsis
========

::

    delete-thing-type
  --thing-type-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-type-name`` (string)


  The name of the thing type.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

