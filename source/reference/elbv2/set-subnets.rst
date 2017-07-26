[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 set-subnets:


***********
set-subnets
***********



===========
Description
===========



Enables the Availability Zone for the specified subnets for the specified load balancer. The specified subnets replace the previously enabled subnets.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/SetSubnets>`_


========
Synopsis
========

::

    set-subnets
  --load-balancer-arn <value>
  --subnets <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--subnets`` (list)


  The IDs of the subnets. You must specify at least two subnets. You can add only one subnet per Availability Zone.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To enable Availability Zones for a load balancer**

This example enables the Availability Zone for the specified subnet for the specified load balancer.

Command::

  aws elbv2 set-subnets --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --subnets subnet-8360a9e7 subnet-b7d581c0

Output::

  {
    "AvailabilityZones": [
        {
            "SubnetId": "subnet-8360a9e7",
            "ZoneName": "us-west-2a"
        },
        {
            "SubnetId": "subnet-b7d581c0",
            "ZoneName": "us-west-2b"
        }
    ]
  }


======
Output
======

AvailabilityZones -> (list)

  

  Information about the subnet and Availability Zone.

  

  (structure)

    

    Information about an Availability Zone.

    

    ZoneName -> (string)

      

      The name of the Availability Zone.

      

      

    SubnetId -> (string)

      

      The ID of the subnet.

      

      

    

  

