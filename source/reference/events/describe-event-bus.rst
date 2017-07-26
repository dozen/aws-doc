[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events describe-event-bus:


******************
describe-event-bus
******************



===========
Description
===========



Displays the external AWS accounts that are permitted to write events to your account using your account's event bus, and the associated policy. To enable your account to receive events from other accounts, use  put-permission .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/DescribeEventBus>`_


========
Synopsis
========

::

    describe-event-bus
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Name -> (string)

  

  The name of the event bus. Currently, this is always ``default`` .

  

  

Arn -> (string)

  

  The Amazon Resource Name (ARN) of the account permitted to write events to the current account.

  

  

Policy -> (string)

  

  The policy that enables the external account to send events to your account.

  

  

