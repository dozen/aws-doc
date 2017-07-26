[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-user-policy:


***************
get-user-policy
***************



===========
Description
===========



Retrieves the specified inline policy document that is embedded in the specified user. 

 

A user can also have managed policies attached to it. To retrieve a managed policy document that is attached to a user, use  get-policy to determine the policy's default version, then use  get-policy-version to retrieve the policy document. 

 

For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    get-user-policy
  --user-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user who the policy is associated with.

  

``--policy-name`` (string)


  The name of the policy document to get.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list policy details for an IAM user**

The following ``get-user-policy`` command lists the details of the specified policy that is attached to the IAM user named ``Bob``::

  aws iam get-user-policy --user-name Bob --policy-name ExamplePolicy

Output::

  {
      "UserName": "Bob",
      "PolicyName": "ExamplePolicy",
      "PolicyDocument": {
          "Version": "2012-10-17",
          "Statement": [
              {
                  "Action": "*",
                  "Resource": "*",
                  "Effect": "Allow"
              }
          ]
      }
  }

To get a list of policies for an IAM user, use the ``list-user-policies`` command.

For more information, see `Adding a New User to Your AWS Account`_ in the *Using IAM* guide.

.. _`Adding a New User to Your AWS Account`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_SettingUpUser.html







======
Output
======

UserName -> (string)

  

  The user the policy is associated with.

  

  

PolicyName -> (string)

  

  The name of the policy.

  

  

PolicyDocument -> (string)

  

  The policy document.

  

  



.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
