[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 describe-load-balancers:


***********************
describe-load-balancers
***********************



===========
Description
===========



Describes the specified Application Load Balancers or all of your Application Load Balancers.

 

To describe the listeners for a load balancer, use  describe-listeners . To describe the attributes for a load balancer, use  describe-load-balancer-attributes .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DescribeLoadBalancers>`_


``describe-load-balancers`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``LoadBalancers``


========
Synopsis
========

::

    describe-load-balancers
  [--load-balancer-arns <value>]
  [--names <value>]
  [--page-size <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arns`` (list)


  The Amazon Resource Names (ARN) of the load balancers. You can specify up to 20 load balancers in a single call.

  



Syntax::

  "string" "string" ...



``--names`` (list)


  The names of the load balancers.

  



Syntax::

  "string" "string" ...



``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a load balancer**

This example describes the specified load balancer.

Command::

  aws elbv2 describe-load-balancers --load-balancer-arns arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188

Output::

  {
    "LoadBalancers": [
        {
            "VpcId": "vpc-3ac0fb5f",
            "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188",
            "State": {
                "Code": "active"
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

**To describe all load balancers**

This example describes all of your load balancers.

Command::

  aws elbv2 describe-load-balancers 


======
Output
======

LoadBalancers -> (list)

  

  Information about the load balancers.

  

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

      

      

    

  

NextMarker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

