[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-role-policy:


***************
get-role-policy
***************



===========
Description
===========



Retrieves the specified inline policy document that is embedded with the specified role. 

 

A role can also have managed policies attached to it. To retrieve a managed policy document that is attached to a role, use  get-policy to determine the policy's default version, then use  get-policy-version to retrieve the policy document. 

 

For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 

 

For more information about roles, go to `Using Roles to Delegate Permissions and Federate Identities`_ . 



========
Synopsis
========

::

    get-role-policy
  --role-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-name`` (string)


  The name of the role associated with the policy.

  

``--policy-name`` (string)


  The name of the policy document to get.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about a policy attached to an IAM role**

The following ``get-role-policy`` command gets information about the specified policy attached to the role named ``Test-Role``::

  aws iam get-role-policy --role-name Test-Role --policy-name ExamplePolicy

Output::

    {
      "RoleName": "Test-Role",
      "PolicyDocument": {
          "Statement": [
              {
                  "Action": [
                      "s3:ListBucket",
                      "s3:Put*",
                      "s3:Get*",
                      "s3:*MultipartUpload*"
                  ],
                  "Resource": "*",
                  "Effect": "Allow",
                  "Sid": "1"
              }
          ]
      }
      "PolicyName": "ExamplePolicy"
    }

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

RoleName -> (string)

  

  The role the policy is associated with.

  

  

PolicyName -> (string)

  

  The name of the policy.

  

  

PolicyDocument -> (string)

  

  The policy document.

  

  



.. _Using Roles to Delegate Permissions and Federate Identities: http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
