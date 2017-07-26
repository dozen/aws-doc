[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-scaling-process-types:


******************************
describe-scaling-process-types
******************************



===========
Description
===========



Describes the scaling process types for use with  resume-processes and  suspend-processes .



========
Synopsis
========

::

    describe-scaling-process-types
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

     

    For more information, see `Auto Scaling Processes`_ in the *Auto Scaling Developer Guide* .

    

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
       

      

      

    

  



.. _Auto Scaling Processes: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US_SuspendResume.html#process-types
