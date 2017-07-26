[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation get-stack-policy:


****************
get-stack-policy
****************



===========
Description
===========



Returns the stack policy for a specified stack. If a stack doesn't have a policy, a null value is returned.



========
Synopsis
========

::

    get-stack-policy
  --stack-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or unique stack ID that is associated with the stack whose policy you want to get.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

StackPolicyBody -> (string)

  

  Structure containing the stack policy body. (For more information, go to `Prevent Updates to Stack Resources`_ in the AWS CloudFormation User Guide.)

  

  



.. _Prevent Updates to Stack Resources: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html
