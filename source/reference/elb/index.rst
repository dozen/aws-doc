[ :ref:`aws <cli:aws>` ]

.. _cli:aws elb:


***
elb
***



===========
Description
===========

 

Elastic Load Balancing distributes incoming traffic across your EC2 instances.

 

For information about the features of Elastic Load Balancing, see `What Is Elastic Load Balancing?`_ in the *Elastic Load Balancing Developer Guide* .

 

For information about the AWS regions supported by Elastic Load Balancing, see `Regions and Endpoints - Elastic Load Balancing`_ in the *Amazon Web Services General Reference* .

 

All Elastic Load Balancing operations are *idempotent* , which means that they complete at most one time. If you repeat an operation, it succeeds with a 200 OK response code.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-tags
  apply-security-groups-to-load-balancer
  attach-load-balancer-to-subnets
  configure-health-check
  create-app-cookie-stickiness-policy
  create-lb-cookie-stickiness-policy
  create-load-balancer
  create-load-balancer-listeners
  create-load-balancer-policy
  delete-load-balancer
  delete-load-balancer-listeners
  delete-load-balancer-policy
  deregister-instances-from-load-balancer
  describe-instance-health
  describe-load-balancer-attributes
  describe-load-balancer-policies
  describe-load-balancer-policy-types
  describe-load-balancers
  describe-tags
  detach-load-balancer-from-subnets
  disable-availability-zones-for-load-balancer
  enable-availability-zones-for-load-balancer
  modify-load-balancer-attributes
  register-instances-with-load-balancer
  remove-tags
  set-load-balancer-listener-ssl-certificate
  set-load-balancer-policies-for-backend-server
  set-load-balancer-policies-of-listener


.. _Regions and Endpoints - Elastic Load Balancing: http://docs.aws.amazon.com/general/latest/gr/rande.html#elb_region
.. _What Is Elastic Load Balancing?: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elastic-load-balancing.html
