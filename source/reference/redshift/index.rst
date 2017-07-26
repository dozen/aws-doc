[ :ref:`aws <cli:aws>` ]

.. _cli:aws redshift:


********
redshift
********



===========
Description
===========

 **Overview**  

This is an interface reference for Amazon Redshift. It contains documentation for one of the programming or command line interfaces you can use to manage Amazon Redshift clusters. Note that Amazon Redshift is asynchronous, which means that some interfaces may require techniques, such as polling or asynchronous callback handlers, to determine when a command has been applied. In this reference, the parameter descriptions indicate whether a change is applied immediately, on the next instance reboot, or during the next maintenance window. For a summary of the Amazon Redshift cluster management interfaces, go to `Using the Amazon Redshift Management Interfaces`_ .

 

Amazon Redshift manages all the work of setting up, operating, and scaling a data warehouse: provisioning capacity, monitoring and backing up the cluster, and applying patches and upgrades to the Amazon Redshift engine. You can focus on using your data to acquire new insights for your business and customers. 

 

If you are a first-time user of Amazon Redshift, we recommend that you begin by reading the The `Amazon Redshift Getting Started Guide`_ 

 

If you are a database developer, the `Amazon Redshift Database Developer Guide`_ explains how to design, build, query, and maintain the databases that make up your data warehouse. 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  authorize-cluster-security-group-ingress
  authorize-snapshot-access
  copy-cluster-snapshot
  create-cluster
  create-cluster-parameter-group
  create-cluster-security-group
  create-cluster-snapshot
  create-cluster-subnet-group
  create-event-subscription
  create-hsm-client-certificate
  create-hsm-configuration
  create-snapshot-copy-grant
  create-tags
  delete-cluster
  delete-cluster-parameter-group
  delete-cluster-security-group
  delete-cluster-snapshot
  delete-cluster-subnet-group
  delete-event-subscription
  delete-hsm-client-certificate
  delete-hsm-configuration
  delete-snapshot-copy-grant
  delete-tags
  describe-cluster-parameter-groups
  describe-cluster-parameters
  describe-cluster-security-groups
  describe-cluster-snapshots
  describe-cluster-subnet-groups
  describe-cluster-versions
  describe-clusters
  describe-default-cluster-parameters
  describe-event-categories
  describe-event-subscriptions
  describe-events
  describe-hsm-client-certificates
  describe-hsm-configurations
  describe-logging-status
  describe-orderable-cluster-options
  describe-reserved-node-offerings
  describe-reserved-nodes
  describe-resize
  describe-snapshot-copy-grants
  describe-tags
  disable-logging
  disable-snapshot-copy
  enable-logging
  enable-snapshot-copy
  modify-cluster
  modify-cluster-parameter-group
  modify-cluster-subnet-group
  modify-event-subscription
  modify-snapshot-copy-retention-period
  purchase-reserved-node-offering
  reboot-cluster
  reset-cluster-parameter-group
  restore-from-cluster-snapshot
  revoke-cluster-security-group-ingress
  revoke-snapshot-access
  rotate-encryption-key
  wait/index


.. _Amazon Redshift Getting Started Guide: http://docs.aws.amazon.com/redshift/latest/gsg/getting-started.html
.. _Amazon Redshift Database Developer Guide: http://docs.aws.amazon.com/redshift/latest/dg/welcome.html
.. _Using the Amazon Redshift Management Interfaces: http://docs.aws.amazon.com/redshift/latest/mgmt/using-aws-sdk.html
