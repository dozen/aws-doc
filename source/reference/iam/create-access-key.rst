[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-access-key:


*****************
create-access-key
*****************



===========
Description
===========



Creates a new AWS secret access key and corresponding AWS access key ID for the specified user. The default status for new keys is ``Active`` .

 

If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

 

For information about limits on the number of keys you can create, see `Limitations on IAM Entities <http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html>`_ in the *IAM User Guide* .

 

.. warning::

   

  To ensure the security of your AWS account, the secret access key is accessible only during key and user creation. You must save the key (for example, in a text file) if you want to be able to access it again. If a secret key is lost, you can delete the access keys for the associated user and then create new keys.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/CreateAccessKey>`_


========
Synopsis
========

::

    create-access-key
  [--user-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user that the new key will belong to.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an access key for an IAM user**

The following ``create-access-key`` command creates an access key (access key ID and secret access key) for the IAM user named ``Bob``::

  aws iam create-access-key --user-name Bob

Output::

  {
      "AccessKey": {
          "UserName": "Bob",
          "Status": "Active",
          "CreateDate": "2015-03-09T18:39:23.411Z",
          "SecretAccessKey": "wJalrXUtnFEMI/K7MDENG/bPxRfiCYzEXAMPLEKEY",
          "AccessKeyId": "AKIAIOSFODNN7EXAMPLE"
      }
  }

Store the secret access key in a secure location. If it is lost, it cannot be recovered, and you must create a new access key.

For more information, see `Managing Access Keys for IAM Users`_ in the *Using IAM* guide.

.. _`Managing Access Keys for IAM Users`: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingCredentials.html

======
Output
======

AccessKey -> (structure)

  

  A structure with details about the access key.

  

  UserName -> (string)

    

    The name of the IAM user that the access key is associated with.

    

    

  AccessKeyId -> (string)

    

    The ID for this access key.

    

    

  Status -> (string)

    

    The status of the access key. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not. 

    

    

  SecretAccessKey -> (string)

    

    The secret key used to sign requests.

    

    

  CreateDate -> (timestamp)

    

    The date when the access key was created.

    

    

  

