[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-termination-policy-types:


*********************************
describe-termination-policy-types
*********************************



===========
Description
===========



Describes the termination policies supported by Auto Scaling.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeTerminationPolicyTypes>`_


========
Synopsis
========

::

    describe-termination-policy-types
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

