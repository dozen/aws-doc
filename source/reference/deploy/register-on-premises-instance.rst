[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy register-on-premises-instance:


*****************************
register-on-premises-instance
*****************************



===========
Description
===========



Registers an on-premises instance.



========
Synopsis
========

::

    register-on-premises-instance
  --instance-name <value>
  --iam-user-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-name`` (string)


  The name of the on-premises instance to register.

  

``--iam-user-arn`` (string)


  The ARN of the IAM user to associate with the on-premises instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To register an on-premises instance**

This example registers an on-premises instance with AWS CodeDeploy. It does not create the specified IAM user, nor does it associate in AWS CodeDeploy any on-premises instances tags with the registered instance.

Command::

  aws deploy register-on-premises-instance --instance-name AssetTag12010298EX --iam-user-arn arn:aws:iam::80398EXAMPLE:user/CodeDeployDemoUser-OnPrem

Output::

  This command produces no output.

======
Output
======

None