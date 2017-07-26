[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-adjustment-types:


*************************
describe-adjustment-types
*************************



===========
Description
===========



Describes the policy adjustment types for use with  put-scaling-policy .



========
Synopsis
========

::

    describe-adjustment-types
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

**To describe the Auto Scaling adjustment types**

This example describes the available adjustment types::

	aws autoscaling describe-adjustment-types

The following is example output::

  {
    "AdjustmentTypes": [
      {
        "AdjustmentType": "ChangeInCapacity"
      }
      {
        "AdjustmentType": "ExactCapcity"
      }
      {
        "AdjustmentType": "PercentChangeInCapacity"
      }
    ]
  }

For more information, see `Scaling Adjustment Types`_ in the *Auto Scaling Developer Guide*.

.. _`Scaling Adjustment Types`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html#as-scaling-adjustment


======
Output
======

AdjustmentTypes -> (list)

  

  The policy adjustment types.

  

  (structure)

    

    Describes a policy adjustment type.

     

    For more information, see `Dynamic Scaling`_ in the *Auto Scaling Developer Guide* .

    

    AdjustmentType -> (string)

      

      The policy adjustment type. The valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

      

      

    

  



.. _Dynamic Scaling: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html
