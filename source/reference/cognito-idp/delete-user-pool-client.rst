[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp delete-user-pool-client:


***********************
delete-user-pool-client
***********************



===========
Description
===========



Allows the developer to delete the user pool client.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/DeleteUserPoolClient>`_


========
Synopsis
========

::

    delete-user-pool-client
  --user-pool-id <value>
  --client-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where you want to delete the client.

  

``--client-id`` (string)


  The ID of the client associated with the user pool.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None