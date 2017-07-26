[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-scaling-process-types:


******************************
describe-scaling-process-types
******************************



===========
Description
===========



Describes the scaling process types for use with  resume-processes and  suspend-processes .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeScalingProcessTypes>`_


========
Synopsis
========

::

    describe-scaling-process-types
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

**To describe the Auto Scaling process types**

This example describes the Auto Scaling process types::

    aws autoscaling describe-scaling-process-types

The following is example output::

    {
        "Processes": [
            {
                "ProcessName": "AZRebalance"
            },
            {
                "ProcessName": "AddToLoadBalancer"
            },
            {
                "ProcessName": "AlarmNotification"
            },
            {
                "ProcessName": "HealthCheck"
            },
            {
                "ProcessName": "Launch"
            },
            {
                "ProcessName": "ReplaceUnhealthy"
            },
            {
                "ProcessName": "ScheduledActions"
            },
            {
                "ProcessName": "Terminate"
            }
        ]
    }

For more information, see `Suspend and Resume Auto Scaling Processes`_ in the *Auto Scaling Developer Guide*.

.. _`Suspend and Resume Auto Scaling Processes`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US_SuspendResume.html


======
Output
======

Processes -> (list)

  

  The names of the process types.

  

  (structure)

    

    Describes a process type.

     

    For more information, see `Auto Scaling Processes <http://docs.aws.amazon.com/autoscaling/latest/userguide/as-suspend-resume-processes.html#process-types>`_ in the *Auto Scaling User Guide* .

    

    ProcessName -> (string)

      

      One of the following processes:

       

       
      * ``Launch``   
       
      * ``Terminate``   
       
      * ``AddToLoadBalancer``   
       
      * ``AlarmNotification``   
       
      * ``AZRebalance``   
       
      * ``HealthCheck``   
       
      * ``ReplaceUnhealthy``   
       
      * ``ScheduledActions``   
       

      

      

    

  

