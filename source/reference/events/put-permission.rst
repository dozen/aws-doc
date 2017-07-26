[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events put-permission:


**************
put-permission
**************



===========
Description
===========



Running ``put-permission`` permits the specified AWS account to put events to your account's default *event bus* . CloudWatch Events rules in your account are triggered by these events arriving to your default event bus. 

 

For another account to send events to your account, that external account must have a CloudWatch Events rule with your account's default event bus as a target.

 

To enable multiple AWS accounts to put events to your default event bus, run ``put-permission`` once for each of these accounts.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/PutPermission>`_


========
Synopsis
========

::

    put-permission
  --action <value>
  --principal <value>
  --statement-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--action`` (string)


  The action that you are enabling the other account to perform. Currently, this must be ``events:PutEvents`` .

  

``--principal`` (string)


  The 12-digit AWS account ID that you are permitting to put events to your default event bus. Specify "*" to permit any account to put events to your default event bus.

   

  If you specify "*", avoid creating rules that may match undesirable events. To create more secure rules, make sure that the event pattern for each rule contains an ``account`` field with a specific account ID from which to receive events. Rules with an account field do not match any events sent from other accounts.

  

``--statement-id`` (string)


  An identifier string for the external account that you are granting permissions to. If you later want to revoke the permission for this external account, specify this ``statement-id`` when you run  remove-permission .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None