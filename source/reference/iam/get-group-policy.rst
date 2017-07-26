[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-group-policy:


****************
get-group-policy
****************



===========
Description
===========



Retrieves the specified inline policy document that is embedded in the specified group. 

 

A group can also have managed policies attached to it. To retrieve a managed policy document that is attached to a group, use  get-policy to determine the policy's default version, then use  get-policy-version to retrieve the policy document. 

 

For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    get-group-policy
  --group-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name of the group the policy is associated with.

  

``--policy-name`` (string)


  The name of the policy document to get.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about a policy attached to an IAM group**

The following ``get-group-policy`` command gets information about the specified policy attached to the group named ``Test-Group``::

  aws iam get-group-policy --group-name Test-Group --policy-name S3-ReadOnly-Policy

Output::

    {
        "GroupName": "Test-Group",
        "PolicyDocument": {
            "Statement": [
                {
                    "Action": [
                        "s3:Get*",
                        "s3:List*"
                    ],
                    "Resource": "*",
                    "Effect": "Allow"
                }
            ]
        },
        "PolicyName": "S3-ReadOnly-Policy"
    }

For more information, see `Managing IAM Policies`_ in the *Using IAM* guide.

.. _`Managing IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingPolicies.html



======
Output
======

GroupName -> (string)

  

  The group the policy is associated with.

  

  

PolicyName -> (string)

  

  The name of the policy.

  

  

PolicyDocument -> (string)

  

  The policy document.

  

  



.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
