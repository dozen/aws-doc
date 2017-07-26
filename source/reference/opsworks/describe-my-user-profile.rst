[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-my-user-profile:


************************
describe-my-user-profile
************************



===========
Description
===========



Describes a user's SSH information.

 

 **Required Permissions** : To use this action, an IAM user must have self-management enabled or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeMyUserProfile>`_


========
Synopsis
========

::

    describe-my-user-profile
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To obtain a user's profile**

The following example shows how to obtain the profile
of the AWS Identity and Access Management (IAM) user that is running the command. ::

  aws opsworks --region us-east-1 describe-user-profile

*Output*: For brevity, most of the user's SSH public key is replaced by an ellipsis (...). ::

  {
    "UserProfile": {
      "IamUserArn": "arn:aws:iam::123456789012:user/myusername", 
      "SshPublicKey": "ssh-rsa AAAAB3NzaC1yc2EAAAABJQ...3LQ4aX9jpxQw== rsa-key-20141104", 
      "Name": "myusername", 
      "SshUsername": "myusername"
    }
  }

**More Information**

For more information, see `Importing Users into AWS OpsWorks`_ in the *AWS OpsWorks User Guide*.

.. _`Importing Users into AWS OpsWorks`: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users-manage-import.html



======
Output
======

UserProfile -> (structure)

  

  A ``UserProfile`` object that describes the user's SSH information.

  

  IamUserArn -> (string)

    

    The user's IAM ARN.

    

    

  Name -> (string)

    

    The user's name.

    

    

  SshUsername -> (string)

    

    The user's SSH user name.

    

    

  SshPublicKey -> (string)

    

    The user's SSH public key.

    

    

  

