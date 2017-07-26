[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 modify-load-balancer-attributes:


*******************************
modify-load-balancer-attributes
*******************************



===========
Description
===========



Modifies the specified attributes of the specified Application Load Balancer.

 

If any of the specified attributes can't be modified as requested, the call fails. Any existing attributes that you do not modify retain their current values.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/ModifyLoadBalancerAttributes>`_


========
Synopsis
========

::

    modify-load-balancer-attributes
  --load-balancer-arn <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--attributes`` (list)


  The load balancer attributes.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
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

**To enable deletion protection**

This example enables deletion protection for the specified load balancer.

Command::

  aws elbv2 modify-load-balancer-attributes --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --attributes Key=deletion_protection.enabled,Value=true

Output::

  {
    "Attributes": [
        {
            "Value": "true",
            "Key": "deletion_protection.enabled"
        },
        {
            "Value": "false",
            "Key": "access_logs.s3.enabled"
        },
        {
            "Value": "60",
            "Key": "idle_timeout.timeout_seconds"
        },
        {
            "Value": "",
            "Key": "access_logs.s3.prefix"
        },
        {
            "Value": "",
            "Key": "access_logs.s3.bucket"
        }
    ]
  }

**To change the idle timeout**

This example changes the idle timeout value for the specified load balancer.

Command::

  aws elbv2 modify-load-balancer-attributes --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --attributes Key=idle_timeout.timeout_seconds,Value=30

Output::

  {
    "Attributes": [
        {
            "Value": "30",
            "Key": "idle_timeout.timeout_seconds"
        },
        {
            "Value": "false",
            "Key": "access_logs.s3.enabled"
        },
        {
            "Value": "",
            "Key": "access_logs.s3.prefix"
        },
        {
            "Value": "true",
            "Key": "deletion_protection.enabled"
        },
        {
            "Value": "",
            "Key": "access_logs.s3.bucket"
        }
    ]
  }

**To enable access logs**

This example enables access logs for the specified load balancer. Note that the S3 bucket must exist in the same region as the load balancer and must have a policy attached that grants access to the Elastic Load Balancing service.

Command::

  aws elbv2 modify-load-balancer-attributes --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --attributes Key=access_logs.s3.enabled,Value=true Key=access_logs.s3.bucket,Value=my-loadbalancer-logs Key=access_logs.s3.prefix,Value=myapp

Output::

  {
    "Attributes": [
        {
            "Value": "true",
            "Key": "access_logs.s3.enabled"
        },
        {
            "Value": "my-load-balancer-logs",
            "Key": "access_logs.s3.bucket"
        },
        {
            "Value": "myapp",
            "Key": "access_logs.s3.prefix"
        },
        {
            "Value": "60",
            "Key": "idle_timeout.timeout_seconds"
        },
        {
            "Value": "false",
            "Key": "deletion_protection.enabled"
        }
    ]
  }


======
Output
======

Attributes -> (list)

  

  Information about the load balancer attributes.

  

  (structure)

    

    Information about a load balancer attribute.

    

    Key -> (string)

      

      The name of the attribute.

       

       
      * ``access_logs.s3.enabled`` - Indicates whether access logs stored in Amazon S3 are enabled. The value is ``true`` or ``false`` . 
       
      * ``access_logs.s3.bucket`` - The name of the S3 bucket for the access logs. This attribute is required if access logs in Amazon S3 are enabled. The bucket must exist in the same region as the load balancer and have a bucket policy that grants Elastic Load Balancing permission to write to the bucket. 
       
      * ``access_logs.s3.prefix`` - The prefix for the location in the S3 bucket. If you don't specify a prefix, the access logs are stored in the root of the bucket. 
       
      * ``deletion_protection.enabled`` - Indicates whether deletion protection is enabled. The value is ``true`` or ``false`` . 
       
      * ``idle_timeout.timeout_seconds`` - The idle timeout value, in seconds. The valid range is 1-3600. The default is 60 seconds. 
       

      

      

    Value -> (string)

      

      The value of the attribute.

      

      

    

  

