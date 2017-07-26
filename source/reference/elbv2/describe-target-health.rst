[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 describe-target-health:


**********************
describe-target-health
**********************



===========
Description
===========



Describes the health of the specified targets or all of your targets.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DescribeTargetHealth>`_


========
Synopsis
========

::

    describe-target-health
  --target-group-arn <value>
  [--targets <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--target-group-arn`` (string)


  The Amazon Resource Name (ARN) of the target group.

  

``--targets`` (list)


  The targets.

  



Shorthand Syntax::

    Id=string,Port=integer ...




JSON Syntax::

  [
    {
      "Id": "string",
      "Port": integer
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

**To describe the health of the targets for a target group**

This example describes the health of the targets for the specified target group. These targets are healthy.

Command::

  aws elbv2 describe-target-health --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067

Output::

  {
    "TargetHealthDescriptions": [
        {
            "HealthCheckPort": "80",
            "Target": {
                "Id": "i-ceddcd4d",
                "Port": 80
            },
            "TargetHealth": {
                "State": "healthy"
            }
        },
        {
            "HealthCheckPort": "80",
            "Target": {
                "Id": "i-0f76fade",
                "Port": 80
            },
            "TargetHealth": {
                "State": "healthy"
            }
        }
    ]
  }

**To describe the health of a target**

This example describes the health of the specified target. This target is healthy.

Command::

  aws elbv2 describe-target-health --targets Id=i-0f76fade,Port=80 --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067

Output::

  {
    "TargetHealthDescriptions": [
        {
            "HealthCheckPort": "80",
            "Target": {
                "Id": "i-0f76fade",
                "Port": 80
            },
            "TargetHealth": {
                "State": "healthy"
            }
        }
    ]
  }

The following is an example response for a target whose target group is not specified in an action for a listener. This target can't receive traffic from the load balancer.

Output::

  {
    "TargetHealthDescriptions": [
        {
            "Target": {
                "Id": "i-0f76fade",
                "Port": 80
            },
            "TargetHealth": {
                "State": "unused",
                "Reason": "Target.NotInUse",
                "Description": "Given target group is not configured to receive traffic from ELB"
            }
        }
    ]
  }

The following is an example response for a target who target group was just specified in an action for a listener. The target is still being registered.

Output::

  {
    "TargetHealthDescriptions": [
        {
            "Target": {
                "Id": "i-0f76fade",
                "Port": 80
            },
            "TargetHealth": {
                "State": "initial",
                "Reason": "Elb.RegistrationInProgress",
                "Description": "Target registration is in progress"
            }
        }
    ]
  }

The following is an example response for an unhealthy target.

Output::

  {
    "TargetHealthDescriptions": [
        {
            "Target": {
                "Id": "i-0f76fade",
                "Port": 80
            },
            "TargetHealth": {
                "State": "unhealthy",
                "Reason": "Target.Timeout",
                "Description": "Connection to target timed out"
            }
        }
    ]
  }


======
Output
======

TargetHealthDescriptions -> (list)

  

  Information about the health of the targets.

  

  (structure)

    

    Information about the health of a target.

    

    Target -> (structure)

      

      The description of the target.

      

      Id -> (string)

        

        The ID of the target.

        

        

      Port -> (integer)

        

        The port on which the target is listening.

        

        

      

    HealthCheckPort -> (string)

      

      The port to use to connect with the target.

      

      

    TargetHealth -> (structure)

      

      The health information for the target.

      

      State -> (string)

        

        The state of the target.

        

        

      Reason -> (string)

        

        The reason code. If the target state is ``healthy`` , a reason code is not provided.

         

        If the target state is ``initial`` , the reason code can be one of the following values:

         

         
        * ``Elb.RegistrationInProgress`` - The target is in the process of being registered with the load balancer. 
         
        * ``Elb.InitialHealthChecking`` - The load balancer is still sending the target the minimum number of health checks required to determine its health status. 
         

         

        If the target state is ``unhealthy`` , the reason code can be one of the following values:

         

         
        * ``Target.ResponseCodeMismatch`` - The health checks did not return an expected HTTP code. 
         
        * ``Target.Timeout`` - The health check requests timed out. 
         
        * ``Target.FailedHealthChecks`` - The health checks failed because the connection to the target timed out, the target response was malformed, or the target failed the health check for an unknown reason. 
         
        * ``Elb.InternalError`` - The health checks failed due to an internal error. 
         

         

        If the target state is ``unused`` , the reason code can be one of the following values:

         

         
        * ``Target.NotRegistered`` - The target is not registered with the target group. 
         
        * ``Target.NotInUse`` - The target group is not used by any load balancer or the target is in an Availability Zone that is not enabled for its load balancer. 
         
        * ``Target.InvalidState`` - The target is in the stopped or terminated state. 
         

         

        If the target state is ``draining`` , the reason code can be the following value:

         

         
        * ``Target.DeregistrationInProgress`` - The target is in the process of being deregistered and the deregistration delay period has not expired. 
         

        

        

      Description -> (string)

        

        A description of the target health that provides additional details. If the state is ``healthy`` , a description is not provided.

        

        

      

    

  

