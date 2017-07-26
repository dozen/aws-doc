[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy deregister:


**********
deregister
**********



===========
Description
===========

Removes any tags from the on-premises instance; deregisters the on-premises instance from AWS CodeDeploy; and, unless requested otherwise, deletes the IAM user for the on-premises instance.



========
Synopsis
========

::

    deregister
  --instance-name <instance-name>
  [--no-delete-iam-user]




=======
Options
=======

``--instance-name`` (string)
Required. The name of the on-premises instance.

``--no-delete-iam-user`` (boolean)
Optional. Do not delete the IAM user for the registered on-premises instance.



========
Examples
========

**To deregister an on-premises instance**

This example deregisters an on-premises instance with AWS CodeDeploy. It does not delete the IAM user that is associated with the instance. It disassociates in AWS CodeDeploy the on-premises tags from the instance. It does not uninstall the AWS CodeDeploy Agent from the instance nor remove the on-premises configuration file from the instance.

Command::

  aws deploy deregister --instance-name AssetTag12010298EX --no-delete-iam-user --region us-west-2

Output::

  Retrieving on-premises instance information... DONE
  IamUserArn: arn:aws:iam::80398EXAMPLE:user/AWS/CodeDeploy/AssetTag12010298EX
  Tags: Key=Name,Value=CodeDeployDemo-OnPrem
  Removing tags from the on-premises instance... DONE
  Deregistering the on-premises instance... DONE
  Run the following command on the on-premises instance to uninstall the codedeploy-agent:
  aws deploy uninstall