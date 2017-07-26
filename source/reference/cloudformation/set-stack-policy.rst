[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation set-stack-policy:


****************
set-stack-policy
****************



===========
Description
===========



Sets a stack policy for a specified stack.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/SetStackPolicy>`_


========
Synopsis
========

::

    set-stack-policy
  --stack-name <value>
  [--stack-policy-body <value>]
  [--stack-policy-url <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or unique stack ID that you want to associate a policy with.

  

``--stack-policy-body`` (string)


  Structure containing the stack policy body. For more information, go to `Prevent Updates to Stack Resources <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html>`_ in the AWS CloudFormation User Guide. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--stack-policy-url`` (string)


  Location of a file containing the stack policy. The URL must point to a policy (maximum size: 16 KB) located in an S3 bucket in the same region as the stack. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None