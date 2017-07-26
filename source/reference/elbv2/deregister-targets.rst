[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 deregister-targets:


******************
deregister-targets
******************



===========
Description
===========



Deregisters the specified targets from the specified target group. After the targets are deregistered, they no longer receive traffic from the load balancer.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DeregisterTargets>`_


========
Synopsis
========

::

    deregister-targets
  --target-group-arn <value>
  --targets <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--target-group-arn`` (string)


  The Amazon Resource Name (ARN) of the target group.

  

``--targets`` (list)


  The targets. If you specified a port override when you registered a target, you must specify both the target ID and the port when you deregister it.

  



Shorthand Syntax::

    Id=string,Port=integer ...




JSON Syntax::

  [
    {
      "Id": "string",
      "Port": integer
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister a target from a target group**

This example deregisters the specified instance from the specified target group.

Command::

  aws elbv2 deregister-targets --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067 --targets Id=i-0f76fade

**To deregister a target registered using port overrides**

This example deregisters an instance that was registered using port overrides.

Command::

  aws elbv2 deregister-targets --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-internal-targets/3bb63f11dfb0faf9 --targets Id=i-80c8dd94,Port=80 Id=i-80c8dd94,Port=766


======
Output
======

