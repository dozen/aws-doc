[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-auto-scaling-instances:


*******************************
describe-auto-scaling-instances
*******************************



===========
Description
===========



Describes one or more Auto Scaling instances. If a list is not provided, the call describes all instances.



``describe-auto-scaling-instances`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``AutoScalingInstances``


========
Synopsis
========

::

    describe-auto-scaling-instances
  [--instance-ids <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-ids`` (list)


  The instances to describe; up to 50 instance IDs. If you omit this parameter, all Auto Scaling instances are described. If you specify an ID that does not exist, it is ignored with no error.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe one or more instances**

This example describes the specified instance::

    aws autoscaling describe-auto-scaling-instances --instance-ids i-4ba0837f

The following is example output::

  {
    "AutoScalingInstances": [
        {
            "InstanceId": "i-4ba0837f",
            "HealthStatus": "HEALTHY",
            "AvailabilityZone": "us-west-2c",
            "AutoScalingGroupName": "my-auto-scaling-group",
            "LifecycleState": "InService"
        }
    ]
  }

This example uses the ``max-items`` parameter to specify how many instances to return with this call::

	aws autoscaling describe-auto-scaling-instances --max-items 1

The following is example output::

  {
    "NextToken": "None___1",
    "AutoScalingInstances": [
        {
            "InstanceId": "i-4ba0837f",
            "HealthStatus": "HEALTHY",
            "AvailabilityZone": "us-west-2c",
            "AutoScalingGroupName": "my-auto-scaling-group",
            "LifecycleState": "InService"
        }
    ]
  }

If the output includes a ``NextToken`` field, there are more instances. To get the additional instances, use the value of this field with the ``starting-token`` parameter in a subsequent call as follows::

    aws autoscaling describe-auto-scaling-instances --starting-token None___1


======
Output
======

AutoScalingInstances -> (list)

  

  The instances.

  

  (structure)

    

    Describes an EC2 instance associated with an Auto Scaling group.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    AutoScalingGroupName -> (string)

      

      The name of the Auto Scaling group associated with the instance.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone for the instance.

      

      

    LifecycleState -> (string)

      

      The lifecycle state for the instance. For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling Developer Guide* .

      

      

    HealthStatus -> (string)

      

      The health status of this instance. "Healthy" means that the instance is healthy and should remain in service. "Unhealthy" means that the instance is unhealthy and Auto Scaling should terminate and replace it.

      

      

    LaunchConfigurationName -> (string)

      

      The launch configuration associated with the instance.

      

      

    ProtectedFromScaleIn -> (boolean)

      

      Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  



.. _Auto Scaling Lifecycle: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingGroupLifecycle.html
