[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-auto-scaling-groups:


****************************
describe-auto-scaling-groups
****************************



===========
Description
===========



Describes one or more Auto Scaling groups.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeAutoScalingGroups>`_


``describe-auto-scaling-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``AutoScalingGroups``


========
Synopsis
========

::

    describe-auto-scaling-groups
  [--auto-scaling-group-names <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-names`` (list)


  The group names. If you omit this parameter, all Auto Scaling groups are described.

  



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

**To get a description of an Auto Scaling group**

This example describes the specified Auto Scaling group::

    aws autoscaling describe-auto-scaling-groups --auto-scaling-group-name my-auto-scaling-group

The following is example output::

    {
        "AutoScalingGroups": [
            {
                "AutoScalingGroupARN": "arn:aws:autoscaling:us-west-2:123456789012:autoScalingGroup:930d940e-891e-4781-a11a-7b0acd480f03:autoScalingGroupName/my-auto-scaling-group",
                "HealthCheckGracePeriod": 300,
                "SuspendedProcesses": [],
                "DesiredCapacity": 1,
                "Tags": [],
                "EnabledMetrics": [],
                "LoadBalancerNames": [],
                "AutoScalingGroupName": "my-auto-scaling-group",
                "DefaultCooldown": 300,
                "MinSize": 0,
                "Instances": [
                    {
                        "InstanceId": "i-4ba0837f",
                        "AvailabilityZone": "us-west-2c",
                        "HealthStatus": "Healthy",
                        "LifecycleState": "InService",
                        "LaunchConfigurationName": "my-launch-config"
                    }
                ],
                "MaxSize": 1,
                "VPCZoneIdentifier": null,
                "TerminationPolicies": [
                    "Default"
                ],
                "LaunchConfigurationName": "my-launch-config",
                "CreatedTime": "2013-08-19T20:53:25.584Z",
                "AvailabilityZones": [
                    "us-west-2c"
                ],
                "HealthCheckType": "EC2",
                "NewInstancesProtectedFromScaleIn": false
            }
        ]
    }

To return a specific number of Auto Scaling groups, use the ``max-items`` parameter::

    aws autoscaling describe-auto-scaling-groups --max-items 1

If the output includes a ``NextToken`` field, there are more groups. To get the additional groups, use the value of this field with the ``starting-token`` parameter in a subsequent call as follows::

    aws autoscaling describe-auto-scaling-groups --starting-token Z3M3LMPEXAMPLE


======
Output
======

AutoScalingGroups -> (list)

  

  The groups.

  

  (structure)

    

    Describes an Auto Scaling group.

    

    AutoScalingGroupName -> (string)

      

      The name of the group.

      

      

    AutoScalingGroupARN -> (string)

      

      The Amazon Resource Name (ARN) of the group.

      

      

    LaunchConfigurationName -> (string)

      

      The name of the associated launch configuration.

      

      

    MinSize -> (integer)

      

      The minimum size of the group.

      

      

    MaxSize -> (integer)

      

      The maximum size of the group.

      

      

    DesiredCapacity -> (integer)

      

      The desired size of the group.

      

      

    DefaultCooldown -> (integer)

      

      The amount of time, in seconds, after a scaling activity completes before another scaling activity can start.

      

      

    AvailabilityZones -> (list)

      

      One or more Availability Zones for the group.

      

      (string)

        

        

      

    LoadBalancerNames -> (list)

      

      One or more load balancers associated with the group.

      

      (string)

        

        

      

    TargetGroupARNs -> (list)

      

      The Amazon Resource Names (ARN) of the target groups for your load balancer.

      

      (string)

        

        

      

    HealthCheckType -> (string)

      

      The service to use for the health checks. The valid values are ``EC2`` and ``ELB`` .

      

      

    HealthCheckGracePeriod -> (integer)

      

      The amount of time, in seconds, that Auto Scaling waits before checking the health status of an EC2 instance that has come into service.

      

      

    Instances -> (list)

      

      The EC2 instances associated with the group.

      

      (structure)

        

        Describes an EC2 instance.

        

        InstanceId -> (string)

          

          The ID of the instance.

          

          

        AvailabilityZone -> (string)

          

          The Availability Zone in which the instance is running.

          

          

        LifecycleState -> (string)

          

          A description of the current lifecycle state. Note that the ``Quarantined`` state is not used.

          

          

        HealthStatus -> (string)

          

          The last reported health status of the instance. "Healthy" means that the instance is healthy and should remain in service. "Unhealthy" means that the instance is unhealthy and Auto Scaling should terminate and replace it.

          

          

        LaunchConfigurationName -> (string)

          

          The launch configuration associated with the instance.

          

          

        ProtectedFromScaleIn -> (boolean)

          

          Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

          

          

        

      

    CreatedTime -> (timestamp)

      

      The date and time the group was created.

      

      

    SuspendedProcesses -> (list)

      

      The suspended processes associated with the group.

      

      (structure)

        

        Describes an Auto Scaling process that has been suspended. For more information, see  ProcessType .

        

        ProcessName -> (string)

          

          The name of the suspended process.

          

          

        SuspensionReason -> (string)

          

          The reason that the process was suspended.

          

          

        

      

    PlacementGroup -> (string)

      

      The name of the placement group into which you'll launch your instances, if any. For more information, see `Placement Groups <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

      

    VPCZoneIdentifier -> (string)

      

      One or more subnet IDs, if applicable, separated by commas.

       

      If you specify ``VPCZoneIdentifier`` and ``AvailabilityZones`` , ensure that the Availability Zones of the subnets match the values for ``AvailabilityZones`` .

      

      

    EnabledMetrics -> (list)

      

      The metrics enabled for the group.

      

      (structure)

        

        Describes an enabled metric.

        

        Metric -> (string)

          

          One of the following metrics:

           

           
          * ``GroupMinSize``   
           
          * ``GroupMaxSize``   
           
          * ``GroupDesiredCapacity``   
           
          * ``GroupInServiceInstances``   
           
          * ``GroupPendingInstances``   
           
          * ``GroupStandbyInstances``   
           
          * ``GroupTerminatingInstances``   
           
          * ``GroupTotalInstances``   
           

          

          

        Granularity -> (string)

          

          The granularity of the metric. The only valid value is ``1Minute`` .

          

          

        

      

    Status -> (string)

      

      The current state of the group when  delete-auto-scaling-group is in progress.

      

      

    Tags -> (list)

      

      The tags for the group.

      

      (structure)

        

        Describes a tag for an Auto Scaling group.

        

        ResourceId -> (string)

          

          The name of the group.

          

          

        ResourceType -> (string)

          

          The type of resource. The only supported value is ``auto-scaling-group`` .

          

          

        Key -> (string)

          

          The tag key.

          

          

        Value -> (string)

          

          The tag value.

          

          

        PropagateAtLaunch -> (boolean)

          

          Determines whether the tag is added to new instances as they are launched in the group.

          

          

        

      

    TerminationPolicies -> (list)

      

      The termination policies for the group.

      

      (string)

        

        

      

    NewInstancesProtectedFromScaleIn -> (boolean)

      

      Indicates whether newly launched instances are protected from termination by Auto Scaling when scaling in.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

