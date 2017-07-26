[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy register-on-premises-instance:


*****************************
register-on-premises-instance
*****************************



===========
Description
===========



Registers an on-premises instance.

 

.. note::

   

  Only one IAM ARN (an IAM session ARN or IAM user ARN) is supported in the request. You cannot use both.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/RegisterOnPremisesInstance>`_


========
Synopsis
========

::

    register-on-premises-instance
  --instance-name <value>
  [--iam-session-arn <value>]
  [--iam-user-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-name`` (string)


  The name of the on-premises instance to register.

  

``--iam-session-arn`` (string)


  The ARN of the IAM session to associate with the on-premises instance.

  

``--iam-user-arn`` (string)


  The ARN of the IAM user to associate with the on-premises instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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