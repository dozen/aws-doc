[ :ref:`aws <cli:aws>` ]

.. _cli:aws elbv2:


*****
elbv2
*****



===========
Description
===========

 

A load balancer distributes incoming traffic across targets, such as your EC2 instances. This enables you to increase the availability of your application. The load balancer also monitors the health of its registered targets and ensures that it routes traffic only to healthy targets. You configure your load balancer to accept incoming traffic by specifying one or more listeners, which are configured with a protocol and port number for connections from clients to the load balancer. You configure a target group with a protocol and port number for connections from the load balancer to the targets, and with health check settings to be used when checking the health status of the targets.

 

Elastic Load Balancing supports two types of load balancers: Classic Load Balancers and Application Load Balancers. A Classic Load Balancer makes routing and load balancing decisions either at the transport layer (TCP/SSL) or the application layer (HTTP/HTTPS), and supports either EC2-Classic or a VPC. An Application Load Balancer makes routing and load balancing decisions at the application layer (HTTP/HTTPS), supports path-based routing, and can route requests to one or more ports on each EC2 instance or container instance in your virtual private cloud (VPC). For more information, see the `Elastic Load Balancing User Guide <http://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/>`_ .

 

This reference covers the 2015-12-01 API, which supports Application Load Balancers. The 2012-06-01 API supports Classic Load Balancers.

 

To get started, complete the following tasks:

 

 
* Create an Application Load Balancer using  create-load-balancer . 
 
* Create a target group using  create-target-group . 
 
* Register targets for the target group using  register-targets . 
 
* Create one or more listeners for your load balancer using  create-listener . 
 
* (Optional) Create one or more rules for content routing based on URL using  create-rule . 
 

 

To delete an Application Load Balancer and its related resources, complete the following tasks:

 

 
* Delete the load balancer using  delete-load-balancer . 
 
* Delete the target group using  delete-target-group . 
 

 

All Elastic Load Balancing operations are idempotent, which means that they complete at most one time. If you repeat an operation, it succeeds.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-tags
  create-listener
  create-load-balancer
  create-rule
  create-target-group
  delete-listener
  delete-load-balancer
  delete-rule
  delete-target-group
  deregister-targets
  describe-account-limits
  describe-listeners
  describe-load-balancer-attributes
  describe-load-balancers
  describe-rules
  describe-ssl-policies
  describe-tags
  describe-target-group-attributes
  describe-target-groups
  describe-target-health
  modify-listener
  modify-load-balancer-attributes
  modify-rule
  modify-target-group
  modify-target-group-attributes
  register-targets
  remove-tags
  set-ip-address-type
  set-rule-priorities
  set-security-groups
  set-subnets
