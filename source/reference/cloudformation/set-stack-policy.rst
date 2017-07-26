[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation set-stack-policy:


****************
set-stack-policy
****************



===========
Description
===========



Sets a stack policy for a specified stack.



========
Synopsis
========

::

    set-stack-policy
  --stack-name <value>
  [--stack-policy-body <value>]
  [--stack-policy-url <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or unique stack ID that you want to associate a policy with.

  

``--stack-policy-body`` (string)


  Structure containing the stack policy body. For more information, go to `Prevent Updates to Stack Resources`_ in the AWS CloudFormation User Guide. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--stack-policy-url`` (string)


  Location of a file containing the stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Prevent Updates to Stack Resources: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html
