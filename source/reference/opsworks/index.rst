[ :ref:`aws <cli:aws>` ]

.. _cli:aws opsworks:


********
opsworks
********



===========
Description
===========

 

Welcome to the *AWS OpsWorks API Reference* . This guide provides descriptions, syntax, and usage examples about AWS OpsWorks actions and data types, including common parameters and error codes. 

 

AWS OpsWorks is an application management service that provides an integrated experience for overseeing the complete application lifecycle. For information about this product, go to the `AWS OpsWorks`_ details page. 

 

 **SDKs and CLI**  

 

The most common way to use the AWS OpsWorks API is by using the AWS Command Line Interface (CLI) or by using one of the AWS SDKs to implement applications in your preferred language. For more information, see:

 

 
* `AWS CLI`_  
 
* `AWS SDK for Java`_  
 
* `AWS SDK for .NET`_  
 
* `AWS SDK for PHP 2`_  
 
* `AWS SDK for Ruby`_  
 
* `AWS SDK for Node.js`_  
 
* `AWS SDK for Python(Boto)`_  
 

 

 **Endpoints**  

 

AWS OpsWorks supports only one endpoint, opsworks.us-east-1.amazonaws.com (HTTPS), so you must connect to that endpoint. You can then use the API to direct AWS OpsWorks to create stacks in any AWS Region.

 

 **Chef Versions**  

 

When you call  create-stack ,  clone-stack , or  update-stack we recommend you use the ``ConfigurationManager`` parameter to specify the Chef version. The recommended value for Linux stacks is currently 12 (the default is 11.4). Windows stacks use Chef 12.2. For more information, see `Chef Versions`_ .

 

.. note::

  You can specify Chef 12, 11.10, or 11.4 for your Linux stack. We recommend migrating your existing Linux stacks to Chef 12 as soon as possible.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  assign-instance
  assign-volume
  associate-elastic-ip
  attach-elastic-load-balancer
  clone-stack
  create-app
  create-deployment
  create-instance
  create-layer
  create-stack
  create-user-profile
  delete-app
  delete-instance
  delete-layer
  delete-stack
  delete-user-profile
  deregister-ecs-cluster
  deregister-elastic-ip
  deregister-instance
  deregister-rds-db-instance
  deregister-volume
  describe-agent-versions
  describe-apps
  describe-commands
  describe-deployments
  describe-ecs-clusters
  describe-elastic-ips
  describe-elastic-load-balancers
  describe-instances
  describe-layers
  describe-load-based-auto-scaling
  describe-my-user-profile
  describe-permissions
  describe-raid-arrays
  describe-rds-db-instances
  describe-service-errors
  describe-stack-provisioning-parameters
  describe-stack-summary
  describe-stacks
  describe-time-based-auto-scaling
  describe-user-profiles
  describe-volumes
  detach-elastic-load-balancer
  disassociate-elastic-ip
  get-hostname-suggestion
  grant-access
  reboot-instance
  register
  register-ecs-cluster
  register-elastic-ip
  register-instance
  register-rds-db-instance
  register-volume
  set-load-based-auto-scaling
  set-permission
  set-time-based-auto-scaling
  start-instance
  start-stack
  stop-instance
  stop-stack
  unassign-instance
  unassign-volume
  update-app
  update-elastic-ip
  update-instance
  update-layer
  update-my-user-profile
  update-rds-db-instance
  update-stack
  update-user-profile
  update-volume


.. _AWS OpsWorks: http://aws.amazon.com/opsworks/
.. _AWS SDK for Node.js: http://aws.amazon.com/documentation/sdkforjavascript/
.. _Chef Versions: http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-chef11.html
.. _AWS SDK for .NET: http://docs.aws.amazon.com/sdkfornet/latest/apidocs/html/N_Amazon_OpsWorks.htm
.. _AWS SDK for Java: http://docs.aws.amazon.com/AWSJavaSDK/latest/javadoc/com/amazonaws/services/opsworks/AWSOpsWorksClient.html
.. _AWS SDK for PHP 2: http://docs.aws.amazon.com/aws-sdk-php-2/latest/class-Aws.OpsWorks.OpsWorksClient.html
.. _AWS CLI: http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html
.. _AWS SDK for Ruby: http://docs.aws.amazon.com/AWSRubySDK/latest/AWS/OpsWorks/Client.html
.. _AWS SDK for Python(Boto): http://docs.pythonboto.org/en/latest/ref/opsworks.html
