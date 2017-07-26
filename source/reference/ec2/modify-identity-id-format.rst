[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-identity-id-format:


*************************
modify-identity-id-format
*************************



===========
Description
===========



Modifies the ID format of a resource for a specified IAM user, IAM role, or the root user for an account; or all IAM users, IAM roles, and the root user for an account. You can specify that resources should receive longer IDs (17-character IDs) when they are created. 

 

The following resource types support longer IDs: ``instance`` | ``reservation`` | ``snapshot`` | ``volume`` . For more information, see `Resource IDs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/resource-ids.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 

 

This setting applies to the principal specified in the request; it does not apply to the principal that makes the request. 

 

Resources created with longer IDs are visible to all IAM roles and users, regardless of these settings and provided that they have permission to use the relevant ``Describe`` command for the resource type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyIdentityIdFormat>`_


========
Synopsis
========

::

    modify-identity-id-format
  --principal-arn <value>
  --resource <value>
  --use-long-ids | --no-use-long-ids
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--principal-arn`` (string)


  The ARN of the principal, which can be an IAM user, IAM role, or the root user. Specify ``all`` to modify the ID format for all IAM users, IAM roles, and the root user of the account.

  

``--resource`` (string)


  The type of resource: ``instance`` | ``reservation`` | ``snapshot`` | ``volume``  

  

``--use-long-ids`` | ``--no-use-long-ids`` (boolean)


  Indicates whether the resource should use longer IDs (17-character IDs)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To enable an IAM role to use longer IDs for a resource**

This example enables the IAM role ``EC2Role`` in your AWS account to use the longer ID format for the ``instance`` resource type. If the request is successful, no output is returned.

Command::

  aws ec2 modify-identity-id-format --principal-arn arn:aws:iam::123456789012:role/EC2Role --resource instance --use-long-ids

**To enable an IAM user to use longer IDs for a resource**

This example enables the IAM user ``AdminUser`` in your AWS account to use the longer ID format for the ``volume`` resource type. If the request is successful, no output is returned.

Command::

  aws ec2 modify-identity-id-format --principal-arn arn:aws:iam::123456789012:user/AdminUser --resource volume --use-long-ids

======
Output
======

None