[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns add-permission:


**************
add-permission
**************



===========
Description
===========



Adds a statement to a topic's access control policy, granting access for the specified AWS accounts to the specified actions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/AddPermission>`_


========
Synopsis
========

::

    add-permission
  --topic-arn <value>
  --label <value>
  --aws-account-id <value>
  --action-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--topic-arn`` (string)


  The ARN of the topic whose access control policy you wish to modify.

  

``--label`` (string)


  A unique identifier for the new policy statement.

  

``--aws-account-id`` (list)


  The AWS account IDs of the users (principals) who will be given access to the specified actions. The users must have AWS accounts, but do not need to be signed up for this service.

  



Syntax::

  "string" "string" ...



``--action-name`` (list)


  The action you want to allow for the specified principal(s).

   

  Valid values: any Amazon SNS action name.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None