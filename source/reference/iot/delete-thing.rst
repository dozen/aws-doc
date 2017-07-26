[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot delete-thing:


************
delete-thing
************



===========
Description
===========



Deletes the specified thing.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DeleteThing>`_


========
Synopsis
========

::

    delete-thing
  --thing-name <value>
  [--expected-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing to delete.

  

``--expected-version`` (long)


  The expected version of the thing record in the registry. If the version of the record in the registry does not match the expected version specified in the request, the ``delete-thing`` request is rejected with a ``VersionConflictException`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

