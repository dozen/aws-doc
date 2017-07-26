[ :ref:`aws <cli:aws>` ]

.. _cli:aws configservice:


*************
configservice
*************



===========
Description
===========

 

AWS Config provides a way to keep track of the configurations of all the AWS resources associated with your AWS account. You can use AWS Config to get the current and historical configurations of each AWS resource and also to get information about the relationship between the resources. An AWS resource can be an Amazon Compute Cloud (Amazon EC2) instance, an Elastic Block Store (EBS) volume, an Elastic network Interface (ENI), or a security group. For a complete list of resources currently supported by AWS Config, see `Supported AWS Resources`_ .

 

You can access and manage AWS Config through the AWS Management Console, the AWS Command Line Interface (AWS CLI), the AWS Config API, or the AWS SDKs for AWS Config

 

This reference guide contains documentation for the AWS Config API and the AWS CLI commands that you can use to manage AWS Config.

 

The AWS Config API uses the Signature Version 4 protocol for signing requests. For more information about how to sign a request with this protocol, see `Signature Version 4 Signing Process`_ .

 

For detailed information about AWS Config features and their associated actions or commands, as well as how to work with AWS Management Console, see `What Is AWS Config?`_ in the *AWS Config Developer Guide* .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  delete-config-rule
  delete-delivery-channel
  deliver-config-snapshot
  describe-compliance-by-config-rule
  describe-compliance-by-resource
  describe-config-rule-evaluation-status
  describe-config-rules
  describe-configuration-recorder-status
  describe-configuration-recorders
  describe-delivery-channel-status
  describe-delivery-channels
  get-compliance-details-by-config-rule
  get-compliance-details-by-resource
  get-compliance-summary-by-config-rule
  get-compliance-summary-by-resource-type
  get-resource-config-history
  get-status
  list-discovered-resources
  put-config-rule
  put-configuration-recorder
  put-delivery-channel
  put-evaluations
  start-configuration-recorder
  stop-configuration-recorder
  subscribe


.. _Signature Version 4 Signing Process: http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html
.. _What Is AWS Config?: http://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html
.. _Supported AWS Resources: http://docs.aws.amazon.com/config/latest/developerguide/resource-config-reference.html#supported-resources
