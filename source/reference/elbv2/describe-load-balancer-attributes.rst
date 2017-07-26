[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 describe-load-balancer-attributes:


*********************************
describe-load-balancer-attributes
*********************************



===========
Description
===========



Describes the attributes for the specified Application Load Balancer.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DescribeLoadBalancerAttributes>`_


========
Synopsis
========

::

    describe-load-balancer-attributes
  --load-balancer-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe load balancer attributes**

This example describes the attributes of the specified load balancer.

Command::

  aws elbv2 describe-load-balancer-attributes --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188

Output::

  {
    "Attributes": [
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
            "Value": "false",
            "Key": "deletion_protection.enabled"
        },
        {
            "Value": "",
            "Key": "access_logs.s3.bucket"
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

      

      

    

  

