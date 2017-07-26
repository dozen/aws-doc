[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-destination-policy:


**********************
put-destination-policy
**********************



===========
Description
===========



Creates or updates an access policy associated with an existing ``Destination`` . An access policy is an `IAM policy document`_ that is used to authorize claims to register a subscription filter against a given destination. 



========
Synopsis
========

::

    put-destination-policy
  --destination-name <value>
  --access-policy <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--destination-name`` (string)


  A name for an existing destination.

  

``--access-policy`` (string)


  An IAM policy document that authorizes cross-account users to deliver their log events to associated destination.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _IAM policy document: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html
