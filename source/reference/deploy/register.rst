[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy register:


********
register
********



===========
Description
===========

Creates an IAM user for the on-premises instance, if not provided, and saves the user's credentials to an on-premises instance configuration file; registers the on-premises instance with AWS CodeDeploy; and optionally adds tags to the on-premises instance.



========
Synopsis
========

::

    register
  --instance-name <instance-name>
  [--tags <value>]
  [--iam-user-arn <iam-user-arn>]




=======
Options
=======

``--instance-name`` (string)
Required. The name of the on-premises instance.

``--tags`` (list)
Optional. The list of key/value pairs to tag the on-premises instance.



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--iam-user-arn`` (string)
Optional. The IAM user associated with the on-premises instance.



========
Examples
========

**To register an on-premises instance**

This example registers an on-premises instance with AWS CodeDeploy, associates in AWS CodeDeploy the specified on-premises instance tag with the registered instance, and creates an on-premises configuration file that can be copied to the instance. It does not create the IAM user, nor does it install the AWS CodeDeploy Agent on the instance.

Command::

  aws deploy register --instance-name AssetTag12010298EX --iam-user-arn arn:aws:iam::80398EXAMPLE:user/CodeDeployUser-OnPrem --tags Key=Name,Value=CodeDeployDemo-OnPrem --region us-west-2

Output::

  Registering the on-premises instance... DONE
  Adding tags to the on-premises instance... DONE
  Copy the on-premises configuration file named codedeploy.onpremises.yml to the on-premises instance, and run the following command on the on-premises instance to install and configure the AWS CodeDeploy Agent:
  aws deploy install --config-file codedeploy.onpremises.yml