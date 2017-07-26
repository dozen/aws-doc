[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-user:


********
get-user
********



===========
Description
===========



Retrieves information about the specified user, including the user's creation date, path, unique ID, and ARN. 

 

If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID used to sign the request. 



========
Synopsis
========

::

    get-user
  [--user-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user to get information about.

   

  This parameter is optional. If it is not included, it defaults to the user making the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about an IAM user**

The following ``get-user`` command gets information about the IAM user named ``Bob``::

  aws iam get-user --user-name Bob

Output::

  {
      "User": {
          "UserName": "Bob",
          "Path": "/",
          "CreateDate": "2012-09-21T23:03:13Z",
          "UserId": "AKIAIOSFODNN7EXAMPLE",
          "Arn": "arn:aws:iam::123456789012:user/Bob"
      }
  }

For more information, see `Listing Users`_ in the *Using IAM* guide.

.. _`Listing Users`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_GetListOfUsers.html




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
