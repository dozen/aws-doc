[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-cross-account-access-role:


**********************************
describe-cross-account-access-role
**********************************



===========
Description
===========



Describes the IAM role that enables Inspector to access your AWS account.



========
Synopsis
========

::

    describe-cross-account-access-role
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

roleArn -> (string)

  

  The ARN specifying the IAM role that Inspector uses to access your AWS account.

  

  

valid -> (boolean)

  

  A Boolean value that specifies whether the IAM role has the necessary policies attached to enable Inspector to access your AWS account.

  

  

