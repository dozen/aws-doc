[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy install:


*******
install
*******



===========
Description
===========

Configures and installs the AWS CodeDeploy Agent on the on-premises instance.



========
Synopsis
========

::

    install
  --config-file <path>
  [--override-config]
  [--agent-installer <s3-location>]




=======
Options
=======

``--config-file`` (string)
Required. The path to the on-premises instance configuration file.

``--override-config`` (boolean)
Optional. Overrides the on-premises instance configuration file.

``--agent-installer`` (string)
Optional. The AWS CodeDeploy Agent installer file.



========
Examples
========

**To install an on-premises instance**

This example copies the on-premises configuration file from the specified location on the instance to the location on the instance that the AWS CodeDeploy Agent expects to find it. It also installs the AWS CodeDeploy Agent on the instance. It does not create any IAM user, nor register the on-premises instance with AWS CodeDeploy, nor associate any on-premises instance tags in AWS CodeDeploy for the instance.

Command::

  aws deploy install --override-config --config-file C:\temp\codedeploy.onpremises.yml --region us-west-2 --agent-installer s3://aws-codedeploy-us-west-2/latest/codedeploy-agent.msi


Output::

  Creating the on-premises instance configuration file... DONE
  Installing the AWS CodeDeploy Agent... DONE