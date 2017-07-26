[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-instance-health:


************************
describe-instance-health
************************



===========
Description
===========



Describes the state of the specified instances with respect to the specified load balancer. If no instances are specified, the call describes the state of all instances that are currently registered with the load balancer. If instances are specified, their state is returned even if they are no longer registered with the load balancer. The state of terminated instances is not returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/DescribeInstanceHealth>`_


========
Synopsis
========

::

    describe-instance-health
  --load-balancer-name <value>
  [--instances <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--instances`` (list)


  The IDs of the instances.

  



Shorthand Syntax::

    --instances InstanceId1 InstanceId2 InstanceId3




JSON Syntax::

  [
    {
      "InstanceId": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the health of the instances for a load balancer**

This example describes the health of the instances for the specified load balancer.

Command::

  aws elb describe-instance-health --load-balancer-name my-load-balancer

Output::

  {
    "InstanceStates": [
        {
            "InstanceId": "i-207d9717",
            "ReasonCode": "N/A",
            "State": "InService",
            "Description": "N/A"
        },
        {
            "InstanceId": "i-afefb49b",
            "ReasonCode": "N/A",
            "State": "InService",
            "Description": "N/A"
        }
    ]
  }

**To describe the health of an instance for a load balancer**

This example describes the health of the specified instance for the specified load balancer.

Command::

  aws elb describe-instance-health --load-balancer-name my-load-balancer --instances i-7299c809

The following is an example response for an instance that is registering.

Output::

  {
    "InstanceStates": [
        {
            "InstanceId": "i-7299c809",
            "ReasonCode": "ELB",
            "State": "OutOfService",
            "Description": "Instance registration is still in progress."
      }
    ]
  }

The following is an example response for an unhealthy instance.

Output::

  {
    "InstanceStates": [
        {
            "InstanceId": "i-7299c809",
            "ReasonCode": "Instance",
            "State": "OutOfService",
            "Description": "Instance has failed at least the UnhealthyThreshold number of health checks consecutively."
        }
    ]
  }


======
Output
======

InstanceStates -> (list)

  

  Information about the health of the instances.

  

  (structure)

    

    Information about the state of an EC2 instance.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    State -> (string)

      

      The current state of the instance.

       

      Valid values: ``InService`` | ``OutOfService`` | ``Unknown``  

      

      

    ReasonCode -> (string)

      

      Information about the cause of ``OutOfService`` instances. Specifically, whether the cause is Elastic Load Balancing or the instance.

       

      Valid values: ``ELB`` | ``Instance`` | ``N/A``  

      

      

    Description -> (string)

      

      A description of the instance state. This string can contain one or more of the following messages.

       

       
      * ``N/A``   
       
      * ``A transient error occurred. Please try again later.``   
       
      * ``Instance has failed at least the UnhealthyThreshold number of health checks consecutively.``   
       
      * ``Instance has not passed the configured HealthyThreshold number of health checks consecutively.``   
       
      * ``Instance registration is still in progress.``   
       
      * ``Instance is in the EC2 Availability Zone for which LoadBalancer is not configured to route traffic to.``   
       
      * ``Instance is not currently registered with the LoadBalancer.``   
       
      * ``Instance deregistration currently in progress.``   
       
      * ``Disable Availability Zone is currently in progress.``   
       
      * ``Instance is in pending state.``   
       
      * ``Instance is in stopped state.``   
       
      * ``Instance is in terminated state.``   
       

      

      

    

  

