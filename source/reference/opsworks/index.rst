[ :ref:`aws <cli:aws>` ]

.. _cli:aws opsworks:


********
opsworks
********



===========
Description
===========

 

Welcome to the *AWS OpsWorks Stacks API Reference* . This guide provides descriptions, syntax, and usage examples for AWS OpsWorks Stacks actions and data types, including common parameters and error codes. 

 

AWS OpsWorks Stacks is an application management service that provides an integrated experience for overseeing the complete application lifecycle. For information about this product, go to the `AWS OpsWorks <http://aws.amazon.com/opsworks/>`_ details page. 

 

 **SDKs and CLI**  

 

The most common way to use the AWS OpsWorks Stacks API is by using the AWS Command Line Interface (CLI) or by using one of the AWS SDKs to implement applications in your preferred language. For more information, see:

 

 
* `AWS CLI <http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html>`_   
 
* `AWS SDK for Java <http://docs.aws.amazon.com/AWSJavaSDK/latest/javadoc/com/amazonaws/services/opsworks/AWSOpsWorksClient.html>`_   
 
* `AWS SDK for .NET <http://docs.aws.amazon.com/sdkfornet/latest/apidocs/html/N_Amazon_OpsWorks.htm>`_   
 
* `AWS SDK for PHP 2 <http://docs.aws.amazon.com/aws-sdk-php-2/latest/class-Aws.OpsWorks.OpsWorksClient.html>`_   
 
* `AWS SDK for Ruby <http://docs.aws.amazon.com/sdkforruby/api/>`_   
 
* `AWS SDK for Node.js <http://aws.amazon.com/documentation/sdkforjavascript/>`_   
 
* `AWS SDK for Python(Boto) <http://docs.pythonboto.org/en/latest/ref/opsworks.html>`_   
 

 

 **Endpoints**  

 

AWS OpsWorks Stacks supports the following endpoints, all HTTPS. You must connect to one of the following endpoints. Stacks can only be accessed or managed within the endpoint in which they are created.

 

 
* opsworks.us-east-1.amazonaws.com 
 
* opsworks.us-east-2.amazonaws.com 
 
* opsworks.us-west-1.amazonaws.com 
 
* opsworks.us-west-2.amazonaws.com 
 
* opsworks.eu-west-1.amazonaws.com 
 
* opsworks.eu-west-2.amazonaws.com 
 
* opsworks.eu-central-1.amazonaws.com 
 
* opsworks.ap-northeast-1.amazonaws.com 
 
* opsworks.ap-northeast-2.amazonaws.com 
 
* opsworks.ap-south-1.amazonaws.com 
 
* opsworks.ap-southeast-1.amazonaws.com 
 
* opsworks.ap-southeast-2.amazonaws.com 
 
* opsworks.sa-east-1.amazonaws.com 
 

 

 **Chef Versions**  

 

When you call  create-stack ,  clone-stack , or  update-stack we recommend you use the ``ConfigurationManager`` parameter to specify the Chef version. The recommended and default value for Linux stacks is currently 12. Windows stacks use Chef 12.2. For more information, see `Chef Versions <http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-chef11.html>`_ .

 

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
  list-tags
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
  tag-resource
  unassign-instance
  unassign-volume
  untag-resource
  update-app
  update-elastic-ip
  update-instance
  update-layer
  update-my-user-profile
  update-rds-db-instance
  update-stack
  update-user-profile
  update-volume
  wait/index
