[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling set-instance-health:


*******************
set-instance-health
*******************



===========
Description
===========



Sets the health status of the specified instance.

 

For more information, see `Health Checks <http://docs.aws.amazon.com/autoscaling/latest/userguide/healthcheck.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/SetInstanceHealth>`_


========
Synopsis
========

::

    set-instance-health
  --instance-id <value>
  --health-status <value>
  [--should-respect-grace-period | --no-should-respect-grace-period]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance.

  

``--health-status`` (string)


  The health status of the instance. Set to ``Healthy`` if you want the instance to remain in service. Set to ``Unhealthy`` if you want the instance to be out of service. Auto Scaling will terminate and replace the unhealthy instance.

  

``--should-respect-grace-period`` | ``--no-should-respect-grace-period`` (boolean)


  If the Auto Scaling group of the specified instance has a ``HealthCheckGracePeriod`` specified for the group, by default, this call will respect the grace period. Set this to ``False`` , if you do not want the call to respect the grace period associated with the group.

   

  For more information, see the description of the health check grace period for  create-auto-scaling-group .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To set the health status of an instance**

This example sets the health status of the specified instance to ``Unhealthy``::

    aws autoscaling set-instance-health --instance-id i-93633f9b --health-status Unhealthy


======
Output
======

None