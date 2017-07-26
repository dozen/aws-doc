[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-adjustment-types:


*************************
describe-adjustment-types
*************************



===========
Description
===========



Describes the policy adjustment types for use with  put-scaling-policy .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeAdjustmentTypes>`_


========
Synopsis
========

::

    describe-adjustment-types
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

**To describe the Auto Scaling adjustment types**

This example describes the available adjustment types::

    aws autoscaling describe-adjustment-types

The following is example output::

    {
        "AdjustmentTypes": [
            {
                "AdjustmentType": "ChangeInCapacity"
            },
            {
                "AdjustmentType": "ExactCapcity"
            },
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

     

    For more information, see `Dynamic Scaling <http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html>`_ in the *Auto Scaling User Guide* .

    

    AdjustmentType -> (string)

      

      The policy adjustment type. The valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

      

      

    

  

