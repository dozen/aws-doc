[ :ref:`aws <cli:aws>` ]

.. _cli:aws rds:


***
rds
***



===========
Description
===========

 

Amazon Relational Database Service (Amazon RDS) is a web service that makes it easier to set up, operate, and scale a relational database in the cloud. It provides cost-efficient, resizeable capacity for an industry-standard relational database and manages common database administration tasks, freeing up developers to focus on what makes their applications and businesses unique. 

 

Amazon RDS gives you access to the capabilities of a MySQL, MariaDB, PostgreSQL, Microsoft SQL Server, Oracle, or Aurora database server. This means the code, applications, and tools you already use today with your existing databases work with Amazon RDS without modification. Amazon RDS automatically backs up your database and maintains the database software that powers your DB instance. Amazon RDS is flexible: you can scale your database instance's compute resources and storage capacity to meet your application's demand. As with all Amazon Web Services, there are no up-front investments, and you pay only for the resources you use. 

 

This is an interface reference for Amazon RDS. It contains documentation for a programming or command line interface you can use to manage Amazon RDS. Note that Amazon RDS is asynchronous, which means that some interfaces might require techniques such as polling or callback functions to determine when a command has been applied. In this reference, the parameter descriptions indicate whether a command is applied immediately, on the next instance reboot, or during the maintenance window. For a summary of the Amazon RDS interfaces, go to `Available RDS Interfaces`_ . 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-option-to-option-group
  add-source-identifier-to-subscription
  add-tags-to-resource
  apply-pending-maintenance-action
  authorize-db-security-group-ingress
  copy-db-cluster-snapshot
  copy-db-parameter-group
  copy-db-snapshot
  copy-option-group
  create-db-cluster
  create-db-cluster-parameter-group
  create-db-cluster-snapshot
  create-db-instance
  create-db-instance-read-replica
  create-db-parameter-group
  create-db-security-group
  create-db-snapshot
  create-db-subnet-group
  create-event-subscription
  create-option-group
  delete-db-cluster
  delete-db-cluster-parameter-group
  delete-db-cluster-snapshot
  delete-db-instance
  delete-db-parameter-group
  delete-db-security-group
  delete-db-snapshot
  delete-db-subnet-group
  delete-event-subscription
  delete-option-group
  describe-account-attributes
  describe-certificates
  describe-db-cluster-parameter-groups
  describe-db-cluster-parameters
  describe-db-cluster-snapshots
  describe-db-clusters
  describe-db-engine-versions
  describe-db-instances
  describe-db-log-files
  describe-db-parameter-groups
  describe-db-parameters
  describe-db-security-groups
  describe-db-snapshot-attributes
  describe-db-snapshots
  describe-db-subnet-groups
  describe-engine-default-cluster-parameters
  describe-engine-default-parameters
  describe-event-categories
  describe-event-subscriptions
  describe-events
  describe-option-group-options
  describe-option-groups
  describe-orderable-db-instance-options
  describe-pending-maintenance-actions
  describe-reserved-db-instances
  describe-reserved-db-instances-offerings
  download-db-log-file-portion
  failover-db-cluster
  list-tags-for-resource
  modify-db-cluster
  modify-db-cluster-parameter-group
  modify-db-instance
  modify-db-parameter-group
  modify-db-snapshot-attribute
  modify-db-subnet-group
  modify-event-subscription
  promote-read-replica
  purchase-reserved-db-instances-offering
  reboot-db-instance
  remove-option-from-option-group
  remove-source-identifier-from-subscription
  remove-tags-from-resource
  reset-db-cluster-parameter-group
  reset-db-parameter-group
  restore-db-cluster-from-snapshot
  restore-db-cluster-to-point-in-time
  restore-db-instance-from-db-snapshot
  restore-db-instance-to-point-in-time
  revoke-db-security-group-ingress
  wait/index


.. _Available RDS Interfaces: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html#Welcome.Interfaces
