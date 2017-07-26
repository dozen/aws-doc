[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 create-load-balancer:


********************
create-load-balancer
********************



===========
Description
===========



Creates an Application Load Balancer.

 

When you create a load balancer, you can specify security groups, subnets, IP address type, and tags. Otherwise, you could do so later using  set-security-groups ,  set-subnets ,  set-ip-address-type , and  add-tags .

 

To create listeners for your load balancer, use  create-listener . To describe your current load balancers, see  describe-load-balancers . When you are finished with a load balancer, you can delete it using  delete-load-balancer .

 

You can create up to 20 load balancers per region per account. You can request an increase for the number of load balancers for your account. For more information, see `Limits for Your Application Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-limits.html>`_ in the *Application Load Balancers Guide* .

 

For more information, see `Application Load Balancers <http://docs.aws.amazon.com/elasticloadbalancing/latest/application/application-load-balancers.html>`_ in the *Application Load Balancers Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/CreateLoadBalancer>`_


========
Synopsis
========

::

    create-load-balancer
  --name <value>
  --subnets <value>
  [--security-groups <value>]
  [--scheme <value>]
  [--tags <value>]
  [--ip-address-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the load balancer.

   

  This name must be unique per region per account, can have a maximum of 32 characters, must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen.

  

``--subnets`` (list)


  The IDs of the subnets to attach to the load balancer. You can specify only one subnet per Availability Zone. You must specify subnets from at least two Availability Zones.

  



Syntax::

  "string" "string" ...



``--security-groups`` (list)


  The IDs of the security groups to assign to the load balancer.

  



Syntax::

  "string" "string" ...



``--scheme`` (string)


  The nodes of an Internet-facing load balancer have public IP addresses. The DNS name of an Internet-facing load balancer is publicly resolvable to the public IP addresses of the nodes. Therefore, Internet-facing load balancers can route requests from clients over the Internet.

   

  The nodes of an internal load balancer have only private IP addresses. The DNS name of an internal load balancer is publicly resolvable to the private IP addresses of the nodes. Therefore, internal load balancers can only route requests from clients with access to the VPC for the load balancer.

   

  The default is an Internet-facing load balancer.

  

  Possible values:

  
  *   ``internet-facing``

  
  *   ``internal``

  

  

``--tags`` (list)


  One or more tags to assign to the load balancer.

  



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



``--ip-address-type`` (string)


  The type of IP addresses used by the subnets for your load balancer. The possible values are ``ipv4`` (for IPv4 addresses) and ``dualstack`` (for IPv4 and IPv6 addresses). Internal load balancers must use ``ipv4`` .

  

  Possible values:

  
  *   ``ipv4``

  
  *   ``dualstack``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an Internet-facing load balancer**

This example creates an Internet-facing load balancer and enables the Availability Zones for the specified subnets.

Command::

  aws elbv2 create-load-balancer --name my-load-balancer --subnets subnet-b7d581c0 subnet-8360a9e7

Output::

  {
    "LoadBalancers": [
        {
            "VpcId": "vpc-3ac0fb5f",
            "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188",
            "State": {
                "Code": "provisioning"
            },
            "DNSName": "my-load-balancer-424835706.us-west-2.elb.amazonaws.com",

            "SecurityGroups": [
                "sg-5943793c"
            ],
            "LoadBalancerName": "my-load-balancer",
            "CreatedTime": "2016-03-25T21:26:12.920Z",
            "Scheme": "internet-facing",
            "Type": "application",
            "CanonicalHostedZoneId": "Z2P70J7EXAMPLE",
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
    ]
  }

**To create an internal load balancer**

This example creates an internal load balancer and enables the Availability Zones for the specified subnets.

Command::

  aws elbv2 create-load-balancer --name my-internal-load-balancer --scheme internal --subnets subnet-b7d581c0 subnet-8360a9e7

Output::

  {
    "LoadBalancers": [
        {
            "VpcId": "vpc-3ac0fb5f",
            "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-internal-load-balancer/5b49b8d4303115c2",
            "State": {
                "Code": "provisioning"
            },
            "DNSName": "internal-my-internal-load-balancer-1529930873.us-west-2.elb.amazonaws.com",
            "SecurityGroups": [
                "sg-5943793c"
            ],
            "LoadBalancerName": "my-internal-load-balancer",
            "CreatedTime": "2016-03-25T21:29:48.850Z",
            "Scheme": "internal",
            "Type": "application",
            "CanonicalHostedZoneId": "Z2P70J7EXAMPLE",
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
    ]
  }


======
Output
======

LoadBalancers -> (list)

  

  Information about the load balancer.

  

  (structure)

    

    Information about a load balancer.

    

    LoadBalancerArn -> (string)

      

      The Amazon Resource Name (ARN) of the load balancer.

      

      

    DNSName -> (string)

      

      The public DNS name of the load balancer.

      

      

    CanonicalHostedZoneId -> (string)

      

      The ID of the Amazon Route 53 hosted zone associated with the load balancer.

      

      

    CreatedTime -> (timestamp)

      

      The date and time the load balancer was created.

      

      

    LoadBalancerName -> (string)

      

      The name of the load balancer.

      

      

    Scheme -> (string)

      

      The nodes of an Internet-facing load balancer have public IP addresses. The DNS name of an Internet-facing load balancer is publicly resolvable to the public IP addresses of the nodes. Therefore, Internet-facing load balancers can route requests from clients over the Internet.

       

      The nodes of an internal load balancer have only private IP addresses. The DNS name of an internal load balancer is publicly resolvable to the private IP addresses of the nodes. Therefore, internal load balancers can only route requests from clients with access to the VPC for the load balancer.

      

      

    VpcId -> (string)

      

      The ID of the VPC for the load balancer.

      

      

    State -> (structure)

      

      The state of the load balancer.

      

      Code -> (string)

        

        The state code. The initial state of the load balancer is ``provisioning`` . After the load balancer is fully set up and ready to route traffic, its state is ``active`` . If the load balancer could not be set up, its state is ``failed`` .

        

        

      Reason -> (string)

        

        A description of the state.

        

        

      

    Type -> (string)

      

      The type of load balancer.

      

      

    AvailabilityZones -> (list)

      

      The Availability Zones for the load balancer.

      

      (structure)

        

        Information about an Availability Zone.

        

        ZoneName -> (string)

          

          The name of the Availability Zone.

          

          

        SubnetId -> (string)

          

          The ID of the subnet.

          

          

        

      

    SecurityGroups -> (list)

      

      The IDs of the security groups for the load balancer.

      

      (string)

        

        

      

    IpAddressType -> (string)

      

      The type of IP addresses used by the subnets for your load balancer. The possible values are ``ipv4`` (for IPv4 addresses) and ``dualstack`` (for IPv4 and IPv6 addresses).

      

      

    

  

