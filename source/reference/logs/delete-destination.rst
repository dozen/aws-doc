[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs delete-destination:


******************
delete-destination
******************



===========
Description
===========



Deletes the specified destination, and eventually disables all the subscription filters that publish to it. This operation does not delete the physical resource encapsulated by the destination.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/DeleteDestination>`_


========
Synopsis
========

::

    delete-destination
  --destination-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--destination-name`` (string)


  The name of the destination.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None