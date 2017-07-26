[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events remove-permission:


*****************
remove-permission
*****************



===========
Description
===========



Revokes the permission of another AWS account to be able to put events to your default event bus. Specify the account to revoke by the ``statement-id`` value that you associated with the account when you granted it permission with ``put-permission`` . You can find the ``statement-id`` by using  describe-event-bus .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/RemovePermission>`_


========
Synopsis
========

::

    remove-permission
  --statement-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--statement-id`` (string)


  The statement ID corresponding to the account that is no longer allowed to put events to the default event bus.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None