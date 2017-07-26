[ :ref:`aws <cli:aws>` ]

.. _cli:aws resourcegroupstaggingapi:


************************
resourcegroupstaggingapi
************************



===========
Description
===========

 

This guide describes the API operations for the resource groups tagging.

 

A tag is a label that you assign to an AWS resource. A tag consists of a key and a value, both of which you define. For example, if you have two Amazon EC2 instances, you might assign both a tag key of "Stack." But the value of "Stack" might be "Testing" for one and "Production" for the other.

 

Tagging can help you organize your resources and enables you to simplify resource management, access management and cost allocation. For more information about tagging, see `Working with Tag Editor <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/tag-editor.html>`_ and `Working with Resource Groups <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/resource-groups.html>`_ . For more information about permissions you need to use the resource groups tagging APIs, see `Obtaining Permissions for Resource Groups <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/obtaining-permissions-for-resource-groups.html>`_ and `Obtaining Permissions for Tagging <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/obtaining-permissions-for-tagging.html>`_ .

 

You can use the resource groups tagging APIs to complete the following tasks:

 

 
* Tag and untag supported resources located in the specified region for the AWS account 
 
* Use tag-based filters to search for resources located in the specified region for the AWS account 
 
* List all existing tag keys in the specified region for the AWS account 
 
* List all existing values for the specified key in the specified region for the AWS account 
 

 

Not all resources can have tags. For a lists of resources that you can tag, see `Supported Resources <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/supported-resources.html>`_ in the *AWS Resource Groups and Tag Editor User Guide* .

 

To make full use of the resource groups tagging APIs, you might need additional IAM permissions, including permission to access the resources of individual services as well as permission to view and apply tags to those resources. For more information, see `Obtaining Permissions for Tagging <http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/obtaining-permissions-for-tagging.html>`_ in the *AWS Resource Groups and Tag Editor User Guide* .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  get-resources
  get-tag-keys
  get-tag-values
  tag-resources
  untag-resources
