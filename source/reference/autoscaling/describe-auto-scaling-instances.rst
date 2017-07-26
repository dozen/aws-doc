[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-auto-scaling-instances:


*******************************
describe-auto-scaling-instances
*******************************



===========
Description
===========



Describes one or more Auto Scaling instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeAutoScalingInstances>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
                "ProtectedFromScaleIn": false,
                "AvailabilityZone": "us-west-2c",
                "InstanceId": "i-4ba0837f",
                "AutoScalingGroupName": "my-auto-scaling-group",
                "HealthStatus": "HEALTHY",
                "LifecycleState": "InService",
                "LaunchConfigurationName": "my-launch-config"
            }
        ]
    }

This example uses the ``max-items`` parameter to specify how many instances to return with this call::

    aws autoscaling describe-auto-scaling-instances --max-items 1

The following is example output::

    {
        "NextToken": "Z3M3LMPEXAMPLE",
        "AutoScalingInstances": [
            {
                "ProtectedFromScaleIn": false,
                "AvailabilityZone": "us-west-2c",
                "InstanceId": "i-4ba0837f",
                "AutoScalingGroupName": "my-auto-scaling-group",
                "HealthStatus": "HEALTHY",
                "LifecycleState": "InService",
                "LaunchConfigurationName": "my-launch-config"
            }
        ]
    }

If the output includes a ``NextToken`` field, there are more instances. To get the additional instances, use the value of this field with the ``starting-token`` parameter in a subsequent call as follows::

    aws autoscaling describe-auto-scaling-instances --starting-token Z3M3LMPEXAMPLE


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

      

      The lifecycle state for the instance. For more information, see `Auto Scaling Lifecycle <http://docs.aws.amazon.com/autoscaling/latest/userguide/AutoScalingGroupLifecycle.html>`_ in the *Auto Scaling User Guide* .

      

      

    HealthStatus -> (string)

      

      The last reported health status of this instance. "Healthy" means that the instance is healthy and should remain in service. "Unhealthy" means that the instance is unhealthy and Auto Scaling should terminate and replace it.

      

      

    LaunchConfigurationName -> (string)

      

      The launch configuration used to launch the instance. This value is not available if you attached the instance to the Auto Scaling group.

      

      

    ProtectedFromScaleIn -> (boolean)

      

      Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

