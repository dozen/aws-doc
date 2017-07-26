[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb create-load-balancer:


********************
create-load-balancer
********************



===========
Description
===========



Creates a Classic Load Balancer.

 

You can add listeners, security groups, subnets, and tags when you create your load balancer, or you can add them later using  create-load-balancer-listeners ,  apply-security-groups-to-load-balancer ,  attach-load-balancer-to-subnets , and  add-tags .

 

To describe your current load balancers, see  describe-load-balancers . When you are finished with a load balancer, you can delete it using  delete-load-balancer .

 

You can create up to 20 load balancers per region per account. You can request an increase for the number of load balancers for your account. For more information, see `Limits for Your Classic Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-limits.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/CreateLoadBalancer>`_


========
Synopsis
========

::

    create-load-balancer
  --load-balancer-name <value>
  --listeners <value>
  [--availability-zones <value>]
  [--subnets <value>]
  [--security-groups <value>]
  [--scheme <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

   

  This name must be unique within your set of load balancers for the region, must have a maximum of 32 characters, must contain only alphanumeric characters or hyphens, and cannot begin or end with a hyphen.

  

``--listeners`` (list)


  The listeners.

   

  For more information, see `listeners for Your Classic Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-listener-config.html>`_ in the *Classic Load Balancer Guide* .

  



Shorthand Syntax::

    Protocol=string,LoadBalancerPort=integer,InstanceProtocol=string,InstancePort=integer,SSLCertificateId=string ...




JSON Syntax::

  [
    {
      "Protocol": "string",
      "LoadBalancerPort": integer,
      "InstanceProtocol": "string",
      "InstancePort": integer,
      "SSLCertificateId": "string"
    }
    ...
  ]



``--availability-zones`` (list)


  One or more Availability Zones from the same region as the load balancer.

   

  You must specify at least one Availability Zone.

   

  You can add more Availability Zones after you create the load balancer using  enable-availability-zones-for-load-balancer .

  



Syntax::

  "string" "string" ...



``--subnets`` (list)


  The IDs of the subnets in your VPC to attach to the load balancer. Specify one subnet per Availability Zone specified in ``availability-zones`` .

  



Syntax::

  "string" "string" ...



``--security-groups`` (list)


  The IDs of the security groups to assign to the load balancer.

  



Syntax::

  "string" "string" ...



``--scheme`` (string)


  The type of a load balancer. Valid only for load balancers in a VPC.

   

  By default, Elastic Load Balancing creates an Internet-facing load balancer with a DNS name that resolves to public IP addresses. For more information about Internet-facing and Internal load balancers, see `Load Balancer Scheme <http://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/how-elastic-load-balancing-works.html#load-balancer-scheme>`_ in the *Elastic Load Balancing User Guide* .

   

  Specify ``internal`` to create a load balancer with a DNS name that resolves to private IP addresses.

  

``--tags`` (list)


  A list of tags to assign to the load balancer.

   

  For more information about tagging your load balancer, see `Tag Your Classic Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/add-remove-tags.html>`_ in the *Classic Load Balancer Guide* .

  



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

**To create an HTTP load balancer**

This example creates a load balancer with an HTTP listener in a VPC.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" --subnets subnet-15aaab61 --security-groups sg-a61988c3

Output::

  {
      "DNSName": "my-load-balancer-1234567890.us-west-2.elb.amazonaws.com"
  }


This example creates a load balancer with an HTTP listener in EC2-Classic.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" --availability-zones us-west-2a us-west-2b

Output::

  {
      "DNSName": "my-load-balancer-123456789.us-west-2.elb.amazonaws.com"
  }

**To create an HTTPS load balancer**

This example creates a load balancer with an HTTPS listener in a VPC.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" "Protocol=HTTPS,LoadBalancerPort=443,InstanceProtocol=HTTP,InstancePort=80,SSLCertificateId=arn:aws:iam::123456789012:server-certificate/my-server-cert" --subnets subnet-15aaab61 --security-groups sg-a61988c3

Output::

  {
      "DNSName": "my-load-balancer-1234567890.us-west-2.elb.amazonaws.com"
  }

This example creates a load balancer with an HTTPS listener in EC2-Classic.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" "Protocol=HTTPS,LoadBalancerPort=443,InstanceProtocol=HTTP,InstancePort=80,SSLCertificateId=arn:aws:iam::123456789012:server-certificate/my-server-cert" --availability-zones us-west-2a us-west-2b

Output::

  {
      "DNSName": "my-load-balancer-123456789.us-west-2.elb.amazonaws.com"
  }

**To create an internal load balancer**

This example creates an internal load balancer with an HTTP listener in a VPC.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" --scheme internal --subnets subnet-a85db0df --security-groups sg-a61988c3

Output::

  {
      "DNSName": "internal-my-load-balancer-123456789.us-west-2.elb.amazonaws.com"
  }



======
Output
======

DNSName -> (string)

  

  The DNS name of the load balancer.

  

  

