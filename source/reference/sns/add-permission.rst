[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns add-permission:


**************
add-permission
**************



===========
Description
===========



Adds a statement to a topic's access control policy, granting access for the specified AWS accounts to the specified actions.



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
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None