[ :ref:`aws <cli:aws>` ]

.. _cli:aws deploy:


******
deploy
******



===========
Description
===========

 **Overview**  

This is the AWS CodeDeploy API Reference. This guide provides descriptions of the AWS CodeDeploy APIs. For additional information, see the `AWS CodeDeploy User Guide`_ .

 **Using the APIs**  

You can use the AWS CodeDeploy APIs to work with the following items:

 

 
* Applications are unique identifiers that AWS CodeDeploy uses to ensure that the correct combinations of revisions, deployment configurations, and deployment groups are being referenced during deployments. You can use the AWS CodeDeploy APIs to create, delete, get, list, and update applications. 
 
* Deployment configurations are sets of deployment rules and deployment success and failure conditions that AWS CodeDeploy uses during deployments. You can use the AWS CodeDeploy APIs to create, delete, get, and list deployment configurations. 
 
* Deployment groups are groups of instances to which application revisions can be deployed. You can use the AWS CodeDeploy APIs to create, delete, get, list, and update deployment groups. 
 
* Instances represent Amazon EC2 instances to which application revisions are deployed. Instances are identified by their Amazon EC2 tags or Auto Scaling group names. Instances belong to deployment groups. You can use the AWS CodeDeploy APIs to get and list instances. 
 
* Deployments represent the process of deploying revisions to instances. You can use the AWS CodeDeploy APIs to create, get, list, and stop deployments. 
 
* Application revisions are archive files that are stored in Amazon S3 buckets or GitHub repositories. These revisions contain source content (such as source code, web pages, executable files, any deployment scripts, and similar) along with an Application Specification file (AppSpec file). (The AppSpec file is unique to AWS CodeDeploy; it defines a series of deployment actions that you want AWS CodeDeploy to execute.) An application revision is uniquely identified by its Amazon S3 object key and its ETag, version, or both (for application revisions that are stored in Amazon S3 buckets) or by its repository name and commit ID (for applications revisions that are stored in GitHub repositories). Application revisions are deployed through deployment groups. You can use the AWS CodeDeploy APIs to get, list, and register application revisions. 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-tags-to-on-premises-instances
  batch-get-application-revisions
  batch-get-applications
  batch-get-deployment-instances
  batch-get-deployments
  batch-get-on-premises-instances
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
  list-on-premises-instances
  push
  register
  register-application-revision
  register-on-premises-instance
  remove-tags-from-on-premises-instances
  stop-deployment
  uninstall
  update-application
  update-deployment-group


.. _AWS CodeDeploy User Guide: http://docs.aws.amazon.com/codedeploy/latest/userguide
