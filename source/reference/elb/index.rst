[ :ref:`aws <cli:aws>` ]

.. _cli:aws elb:


***
elb
***



===========
Description
===========

 

A load balancer distributes incoming traffic across your EC2 instances. This enables you to increase the availability of your application. The load balancer also monitors the health of its registered instances and ensures that it routes traffic only to healthy instances. You configure your load balancer to accept incoming traffic by specifying one or more listeners, which are configured with a protocol and port number for connections from clients to the load balancer and a protocol and port number for connections from the load balancer to the instances.

 

Elastic Load Balancing supports two types of load balancers: Classic Load Balancers and Application Load Balancers (new). A Classic Load Balancer makes routing and load balancing decisions either at the transport layer (TCP/SSL) or the application layer (HTTP/HTTPS), and supports either EC2-Classic or a VPC. An Application Load Balancer makes routing and load balancing decisions at the application layer (HTTP/HTTPS), supports path-based routing, and can route requests to one or more ports on each EC2 instance or container instance in your virtual private cloud (VPC). For more information, see the `Elastic Load Balancing User Guide <http://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html>`_ .

 

This reference covers the 2012-06-01 API, which supports Classic Load Balancers. The 2015-12-01 API supports Application Load Balancers.

 

To get started, create a load balancer with one or more listeners using  create-load-balancer . Register your instances with the load balancer using  register-instances-with-load-balancer .

 

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
  describe-account-limits
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
  wait/index
