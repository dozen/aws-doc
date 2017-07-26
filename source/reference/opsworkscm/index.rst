[ :ref:`aws <cli:aws>` ]

.. _cli:aws opsworkscm:


**********
opsworkscm
**********



===========
Description
===========

 

AWS OpsWorks for Chef Automate is a service that runs and manages configuration management servers. 

 

 **Glossary of terms**  

 

 
* **Server** : A configuration management server that can be highly-available. The configuration manager runs on your instances by using various AWS services, such as Amazon Elastic Compute Cloud (EC2), and potentially Amazon Relational Database Service (RDS). A server is a generic abstraction over the configuration manager that you want to use, much like Amazon RDS. In AWS OpsWorks for Chef Automate, you do not start or stop servers. After you create servers, they continue to run until they are deleted. 
 
* **Engine** : The specific configuration manager that you want to use (such as ``Chef`` ) is the engine. 
 
* **Backup** : This is an application-level backup of the data that the configuration manager stores. A backup creates a .tar.gz file that is stored in an Amazon Simple Storage Service (S3) bucket in your account. AWS OpsWorks for Chef Automate creates the S3 bucket when you launch the first instance. A backup maintains a snapshot of all of a server's important attributes at the time of the backup. 
 
* **Events** : Events are always related to a server. Events are written during server creation, when health checks run, when backups are created, etc. When you delete a server, the server's events are also deleted. 
 
* **AccountAttributes** : Every account has attributes that are assigned in the AWS OpsWorks for Chef Automate database. These attributes store information about configuration limits (servers, backups, etc.) and your customer account.  
 

 

 **Endpoints**  

 

AWS OpsWorks for Chef Automate supports the following endpoints, all HTTPS. You must connect to one of the following endpoints. Chef servers can only be accessed or managed within the endpoint in which they are created.

 

 
* opsworks-cm.us-east-1.amazonaws.com 
 
* opsworks-cm.us-west-2.amazonaws.com 
 
* opsworks-cm.eu-west-1.amazonaws.com 
 

 

 **Throttling limits**  

 

All API operations allow for five requests per second with a burst of 10 requests per second.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  associate-node
  create-backup
  create-server
  delete-backup
  delete-server
  describe-account-attributes
  describe-backups
  describe-events
  describe-node-association-status
  describe-servers
  disassociate-node
  restore-server
  start-maintenance
  update-server
  update-server-engine-attributes
  wait/index
