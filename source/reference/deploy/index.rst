[ :ref:`aws <cli:aws>` ]

.. _cli:aws deploy:


******
deploy
******



===========
Description
===========

 

AWS CodeDeploy is a deployment service that automates application deployments to Amazon EC2 instances or on-premises instances running in your own facility.

 

You can deploy a nearly unlimited variety of application content, such as code, web and configuration files, executables, packages, scripts, multimedia files, and so on. AWS CodeDeploy can deploy application content stored in Amazon S3 buckets, GitHub repositories, or Bitbucket repositories. You do not need to make changes to your existing code before you can use AWS CodeDeploy.

 

AWS CodeDeploy makes it easier for you to rapidly release new features, helps you avoid downtime during application deployment, and handles the complexity of updating your applications, without many of the risks associated with error-prone manual deployments.

 

 **AWS CodeDeploy Components**  

 

Use the information in this guide to help you work with the following AWS CodeDeploy components:

 

 
* **Application** : A name that uniquely identifies the application you want to deploy. AWS CodeDeploy uses this name, which functions as a container, to ensure the correct combination of revision, deployment configuration, and deployment group are referenced during a deployment. 
 
* **Deployment group** : A set of individual instances. A deployment group contains individually tagged instances, Amazon EC2 instances in Auto Scaling groups, or both.  
 
* **Deployment configuration** : A set of deployment rules and deployment success and failure conditions used by AWS CodeDeploy during a deployment. 
 
* **Deployment** : The process, and the components involved in the process, of installing content on one or more instances.  
 
* **Application revisions** : An archive file containing source content—source code, web pages, executable files, and deployment scripts—along with an application specification file (AppSpec file). Revisions are stored in Amazon S3 buckets or GitHub repositories. For Amazon S3, a revision is uniquely identified by its Amazon S3 object key and its ETag, version, or both. For GitHub, a revision is uniquely identified by its commit ID. 
 

 

This guide also contains information to help you get details about the instances in your deployments and to make on-premises instances available for AWS CodeDeploy deployments.

 

 **AWS CodeDeploy Information Resources**  

 

 
* `AWS CodeDeploy User Guide <http://docs.aws.amazon.com/codedeploy/latest/userguide>`_   
 
* `AWS CodeDeploy API Reference Guide <http://docs.aws.amazon.com/codedeploy/latest/APIReference/>`_   
 
* `AWS CLI Reference for AWS CodeDeploy <http://docs.aws.amazon.com/cli/latest/reference/deploy/index.html>`_   
 
* `AWS CodeDeploy Developer Forum <https://forums.aws.amazon.com/forum.jspa?forumID=179>`_   
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-tags-to-on-premises-instances
  batch-get-application-revisions
  batch-get-applications
  batch-get-deployment-groups
  batch-get-deployment-instances
  batch-get-deployments
  batch-get-on-premises-instances
  continue-deployment
  create-application
  create-deployment
  create-deployment-config
  create-deployment-group
  delete-application
  delete-deployment-config
  delete-deployment-group
  deregister
  deregister-on-premises-instance
  get-application
  get-application-revision
  get-deployment
  get-deployment-config
  get-deployment-group
  get-deployment-instance
  get-on-premises-instance
  install
  list-application-revisions
  list-applications
  list-deployment-configs
  list-deployment-groups
  list-deployment-instances
  list-deployments
  list-git-hub-account-token-names
  list-on-premises-instances
  push
  register
  register-application-revision
  register-on-premises-instance
  remove-tags-from-on-premises-instances
  skip-wait-time-for-instance-termination
  stop-deployment
  uninstall
  update-application
  update-deployment-group
  wait/index
