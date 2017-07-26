[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-user:


***********
create-user
***********



===========
Description
===========



Creates a new user for your AWS account.

 

For information about limitations on the number of users you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    create-user
  [--path <value>]
  --user-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--path`` (string)


  The path for the user name. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

  

``--user-name`` (string)


  The name of the user to create.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an IAM user**

The following ``create-user`` command creates an IAM user named ``Bob`` in the current account::

  aws iam create-user --user-name Bob

Output::

  {
      "User": {
          "UserName": "Bob",
          "Path": "/",
          "CreateDate": "2013-06-08T03:20:41.270Z",
          "UserId": "AKIAIOSFODNN7EXAMPLE",
          "Arn": "arn:aws:iam::123456789012:user/Bob"
      }
  }

For more information, see `Adding a New User to Your AWS Account`_ in the *Using IAM* guide.

.. _`Adding a New User to Your AWS Account`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_SettingUpUser.html



======
Output
======

User -> (structure)

  

  Information about the user.

  

  Path -> (string)

    

    The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

    

    

  UserName -> (string)

    

    The friendly name identifying the user.

    

    

  UserId -> (string)

    

    The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

    

    

  CreateDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format`_ , when the user was created.

    

    

  PasswordLastUsed -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

     

     
    * The user does not have a password 
     
    * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
     
    * there is no sign-in data associated with the user 
     

     

    This value is returned only in the  get-user and  list-users actions. 

    

    

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Credential Reports: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
