[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-permissions:


********************
describe-permissions
********************



===========
Description
===========



Describes the permissions for a specified stack.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-permissions
  [--iam-user-arn <value>]
  [--stack-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--iam-user-arn`` (string)


  The user's IAM ARN. For more information about IAM ARNs, see `Using Identifiers`_ .

  

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To obtain a user's per-stack AWS OpsWorks permission level**

The following example shows how to to obtain an AWS Identity and Access Management (IAM) user's permission level on a specified stack. ::

  aws opsworks --region us-east-1 describe-permissions --iam-user-arn arn:aws:iam::123456789012:user/cli-user-test --stack-id d72553d4-8727-448c-9b00-f024f0ba1b06

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*::

  {
    "Permissions": [
      {
        "StackId": "d72553d4-8727-448c-9b00-f024f0ba1b06", 
        "IamUserArn": "arn:aws:iam::123456789012:user/cli-user-test", 
        "Level": "manage", 
        "AllowSudo": true, 
        "AllowSsh": true
      }
    ]
  }


**More Information**

For more information, see `Granting Per-Stack Permissions Levels`_ in the *AWS OpsWorks User Guide*.

.. _`Granting Per-Stack Permissions Levels`: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users-console.html


======
Output
======

Permissions -> (list)

  

  An array of ``Permission`` objects that describe the stack permissions.

   

   
  * If the request object contains only a stack ID, the array contains a ``Permission`` object with permissions for each of the stack IAM ARNs.
   
  * If the request object contains only an IAM ARN, the array contains a ``Permission`` object with permissions for each of the user's stack IDs.
   
  * If the request contains a stack ID and an IAM ARN, the array contains a single ``Permission`` object with permissions for the specified stack and IAM ARN.
   

  

  (structure)

    

    Describes stack or user permissions.

    

    StackId -> (string)

      

      A stack ID.

      

      

    IamUserArn -> (string)

      

      The Amazon Resource Name (ARN) for an AWS Identity and Access Management (IAM) role. For more information about IAM ARNs, see `Using Identifiers`_ .

      

      

    AllowSsh -> (boolean)

      

      Whether the user can use SSH.

      

      

    AllowSudo -> (boolean)

      

      Whether the user can use **sudo** .

      

      

    Level -> (string)

      

      The user's permission level, which must be the following:

       

       
      * ``deny``  
       
      * ``show``  
       
      * ``deploy``  
       
      * ``manage``  
       
      * ``iam_only``  
       

       

      For more information on the permissions associated with these levels, see `Managing User Permissions`_ 

      

      

    

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Using Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
