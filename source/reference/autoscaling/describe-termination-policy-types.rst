[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-termination-policy-types:


*********************************
describe-termination-policy-types
*********************************



===========
Description
===========



Describes the termination policies supported by Auto Scaling.



========
Synopsis
========

::

    describe-termination-policy-types
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe termination policy types**

This example describes the available termination policy types::

	aws autoscaling describe-termination-policy-types

The following is example output::

  {
    "TerminationPolicyTypes": [
        "ClosestToNextInstanceHour",
        "Default",
        "NewestInstance",
        "OldestInstance",
        "OldestLaunchConfiguration"
    ]
  }

For more information, see `Controlling Which Instances Auto Scaling Terminates During Scale In`_ in the *Auto Scaling Developer Guide*.

.. _`Controlling Which Instances Auto Scaling Terminates During Scale In`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingBehavior.InstanceTermination.html#your-termination-policy


======
Output
======

TerminationPolicyTypes -> (list)

  

  The termination policies supported by Auto Scaling (``OldestInstance`` , ``OldestLaunchConfiguration`` , ``NewestInstance`` , ``ClosestToNextInstanceHour`` , and ``Default`` ).

  

  (string)

    

    

  

