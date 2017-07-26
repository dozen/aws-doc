[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation get-stack-policy:


****************
get-stack-policy
****************



===========
Description
===========



Returns the stack policy for a specified stack. If a stack doesn't have a policy, a null value is returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/GetStackPolicy>`_


========
Synopsis
========

::

    get-stack-policy
  --stack-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or unique stack ID that is associated with the stack whose policy you want to get.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StackPolicyBody -> (string)

  

  Structure containing the stack policy body. (For more information, go to `Prevent Updates to Stack Resources <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html>`_ in the AWS CloudFormation User Guide.)

  

  

