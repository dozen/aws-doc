[ :ref:`aws <cli:aws>` ]

.. _cli:aws discovery:


*********
discovery
*********



===========
Description
===========

 

AWS Application Discovery Service helps you plan application migration projects by automatically identifying servers, virtual machines (VMs), software, and software dependencies running in your on-premises data centers. Application Discovery Service also collects application performance data, which can help you assess the outcome of your migration. The data collected by Application Discovery Service is securely retained in an Amazon-hosted and managed database in the cloud. You can export the data as a CSV or XML file into your preferred visualization tool or cloud-migration solution to plan your migration. For more information, see the Application Discovery Service `FAQ <http://aws.amazon.com/application-discovery/faqs/>`_ .

 

Application Discovery Service offers two modes of operation.

 

 
* **Agentless discovery** mode is recommended for environments that use VMware vCenter Server. This mode doesn't require you to install an agent on each host. Agentless discovery gathers server information regardless of the operating systems, which minimizes the time required for initial on-premises infrastructure assessment. Agentless discovery doesn't collect information about software and software dependencies. It also doesn't work in non-VMware environments. We recommend that you use agent-based discovery for non-VMware environments and if you want to collect information about software and software dependencies. You can also run agent-based and agentless discovery simultaneously. Use agentless discovery to quickly complete the initial infrastructure assessment and then install agents on select hosts to gather information about software and software dependencies. 
 
* **Agent-based discovery** mode collects a richer set of data than agentless discovery by using Amazon software, the AWS Application Discovery Agent, which you install on one or more hosts in your data center. The agent captures infrastructure and application information, including an inventory of installed software applications, system and process performance, resource utilization, and network dependencies between workloads. The information collected by agents is secured at rest and in transit to the Application Discovery Service database in the cloud.  
 

 

Application Discovery Service integrates with application discovery solutions from AWS Partner Network (APN) partners. Third-party application discovery tools can query Application Discovery Service and write to the Application Discovery Service database using a public API. You can then import the data into either a visualization tool or cloud-migration solution.

 

.. warning::

   

  Application Discovery Service doesn't gather sensitive information. All data is handled according to the `AWS Privacy Policy <http://aws.amazon.com/privacy/>`_ . You can operate Application Discovery Service using offline mode to inspect collected data before it is shared with the service.

   

 

Your AWS account must be granted access to Application Discovery Service, a process called *whitelisting* . This is true for AWS partners and customers alike. To request access, sign up for AWS Application Discovery Service `here <http://aws.amazon.com/application-discovery/preview/>`_ . We send you information about how to get started.

 

This API reference provides descriptions, syntax, and usage examples for each of the actions and data types for Application Discovery Service. The topic for each action shows the API request parameters and the response. Alternatively, you can use one of the AWS SDKs to access an API that is tailored to the programming language or platform that you're using. For more information, see `AWS SDKs <http://aws.amazon.com/tools/#SDKs>`_ .

 

This guide is intended for use with the ` *AWS Application Discovery Service User Guide* http://docs.aws.amazon.com/application-discovery/latest/userguide/`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  associate-configuration-items-to-application
  create-application
  create-tags
  delete-applications
  delete-tags
  describe-agents
  describe-configurations
  describe-export-configurations
  describe-export-tasks
  describe-tags
  disassociate-configuration-items-from-application
  export-configurations
  get-discovery-summary
  list-configurations
  list-server-neighbors
  start-data-collection-by-agent-ids
  start-export-task
  stop-data-collection-by-agent-ids
  update-application


.. _http://docs.aws.amazon.com/application-discovery/latest/userguide/: http://docs.aws.amazon.com/application-discovery/latest/userguide/
