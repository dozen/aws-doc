[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb create-load-balancer:


********************
create-load-balancer
********************



===========
Description
===========



Creates a load balancer.

 

If the call completes successfully, a new load balancer is created with a unique Domain Name Service (DNS) name. The load balancer receives incoming traffic and routes it to the registered instances. For more information, see `How Elastic Load Balancing Works`_ in the *Elastic Load Balancing Developer Guide* .

 

You can create up to 20 load balancers per region per account. You can request an increase for the number of load balancers for your account. For more information, see `Elastic Load Balancing Limits`_ in the *Elastic Load Balancing Developer Guide* .



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
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

   

  This name must be unique within your set of load balancers for the region, must have a maximum of 32 characters, must contain only alphanumeric characters or hyphens, and cannot begin or end with a hyphen.

  

``--listeners`` (list)


  The listeners.

   

  For more information, see `listeners for Your Load Balancer`_ in the *Elastic Load Balancing Developer Guide* .

  



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


  One or more Availability Zones from the same region as the load balancer. Traffic is equally distributed across all specified Availability Zones.

   

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

   

  By default, Elastic Load Balancing creates an Internet-facing load balancer with a publicly resolvable DNS name, which resolves to public IP addresses. For more information about Internet-facing and Internal load balancers, see `Internet-facing and Internal Load Balancers`_ in the *Elastic Load Balancing Developer Guide* .

   

  Specify ``internal`` to create an internal load balancer with a DNS name that resolves to private IP addresses.

  

``--tags`` (list)


  A list of tags to assign to the load balancer.

   

  For more information about tagging your load balancer, see `Tagging`_ in the *Elastic Load Balancing Developer Guide* .

  



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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an HTTP load balancer**

This example creates an HTTP load balancer in a VPC.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" --subnets subnet-15aaab61 --security-groups sg-a61988c3

Output::

  {
      "DNSName": "my-load-balancer-1234567890.us-west-2.elb.amazonaws.com"
  }


This example creates an HTTP load balancer in EC2-Classic.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" --availability-zones us-west-2a us-west-2b

Output::

  {
      "DNSName": "my-load-balancer-123456789.us-west-2.elb.amazonaws.com"
  }

**To create an HTTPS load balancer**

This example creates an HTTPS load balancer in a VPC.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" "Protocol=HTTPS,LoadBalancerPort=443,InstanceProtocol=HTTPS,InstancePort=443,SSLCertificateId=arn:aws:iam::123456789012:server-certificate/my-server-cert" --subnets subnet-15aaab61 --security-groups sg-a61988c3

Output::

  {
      "DNSName": "my-load-balancer-1234567890.us-west-2.elb.amazonaws.com"
  }

This example creates an HTTPS load balancer in EC2-Classic.

Command::

  aws elb create-load-balancer --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80" "Protocol=HTTPS,LoadBalancerPort=443,InstanceProtocol=HTTPS,InstancePort=443,SSLCertificateId=arn:aws:iam::123456789012:server-certificate/my-server-cert" --availability-zones us-west-2a us-west-2b

Output::

  {
      "DNSName": "my-load-balancer-123456789.us-west-2.elb.amazonaws.com"
  }

**To create an internal load balancer**

This example creates an internal HTTP load balancer in a VPC.

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

  

  



.. _listeners for Your Load Balancer: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-listener-config.html
.. _Tagging: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/TerminologyandKeyConcepts.html#tagging-elb
.. _Internet-facing and Internal Load Balancers: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/vpc-loadbalancer-types.html
.. _How Elastic Load Balancing Works: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/how-elb-works.html
.. _Elastic Load Balancing Limits: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-limits.html
