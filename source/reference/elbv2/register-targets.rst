[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 register-targets:


****************
register-targets
****************



===========
Description
===========



Registers the specified targets with the specified target group.

 

By default, the load balancer routes requests to registered targets using the protocol and port number for the target group. Alternatively, you can override the port for a target when you register it.

 

The target must be in the virtual private cloud (VPC) that you specified for the target group. If the target is an EC2 instance, it must be in the ``running`` state when you register it.

 

To remove a target from a target group, use  deregister-targets .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/RegisterTargets>`_


========
Synopsis
========

::

    register-targets
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


  The targets. The default port for a target is the port for the target group. You can specify a port override. If a target is already registered, you can register it again using a different port.

  



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

**To register targets with a target group**

This example registers the specified instances with the specified target group.

Command::

  aws elbv2 register-targets --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067 --targets Id=i-80c8dd94 Id=i-ceddcd4d 

**To register targets with a target group using port overrides**

This example registers the specified instance with the specified target group using multiple ports. This enables you to register ECS containers on the same instance as targets in the target group.

Command::

  aws elbv2 register-targets --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-internal-targets/3bb63f11dfb0faf9 --targets Id=i-80c8dd94,Port=80 Id=i-80c8dd94,Port=766


======
Output
======

