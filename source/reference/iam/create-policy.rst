[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-policy:


*************
create-policy
*************



===========
Description
===========



Creates a new managed policy for your AWS account. 

 

This operation creates a policy version with a version identifier of ``v1`` and sets v1 as the policy's default version. For more information about policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* . 

 

For more information about managed policies in general, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    create-policy
  --policy-name <value>
  [--path <value>]
  --policy-document <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy document.

  

``--path`` (string)


  The path for the policy. 

   

  For more information about paths, see `IAM Identifiers`_ in the *IAM User Guide* . 

   

  This parameter is optional. If it is not included, it defaults to a slash (/). 

  

``--policy-document`` (string)


  The policy document.

  

``--description`` (string)


  A friendly description of the policy. 

   

  Typically used to store information about the permissions defined in the policy. For example, "Grants access to production DynamoDB tables." 

   

  The policy description is immutable. After a value is assigned, it cannot be changed. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command creates a customer managed policy named ``my-policy``::

  aws iam create-policy --policy-name my-policy --policy-document file://policy

Output::

  {
      "Policy": {
          "PolicyName": "my-policy",
          "CreateDate": "2015-06-01T19:31:18.620Z",
          "AttachmentCount": 0,
          "IsAttachable": true,
          "PolicyId": "ZXR6A36LTYANPAI7NJ5UV",
          "DefaultVersionId": "v1",
          "Path": "/",
          "Arn": "arn:aws:iam::0123456789012:policy/my-policy",
          "UpdateDate": "2015-06-01T19:31:18.620Z"
      }
  }

The file ``policy`` is a JSON document in the current folder that grants read only access to the ``shared`` folder in an Amazon S3 bucket named ``my-bucket``::

  {
      "Version": "2012-10-17",
      "Statement": [
          {
              "Effect": "Allow",
              "Action": [
                  "s3:Get*",
                  "s3:List*"
              ],
              "Resource": [
                  "arn:aws:s3:::my-bucket/shared/*"
              ]
          },
      ]
  }

For more information on using files as input for string parameters, see `Specifying Parameter Values`_ in the *AWS CLI User Guide*.

.. _`Specifying Parameter Values`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html


======
Output
======

Policy -> (structure)

  

  Information about the policy.

  

  PolicyName -> (string)

    

    The friendly name (not ARN) identifying the policy.

    

    

  PolicyId -> (string)

    

    The stable and unique string identifying the policy. 

     

    For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

     

    For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

    

    

  Path -> (string)

    

    The path to the policy.

     

    For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

    

    

  DefaultVersionId -> (string)

    

    The identifier for the version of the policy that is set as the default version. 

    

    

  AttachmentCount -> (integer)

    

    The number of entities (users, groups, and roles) that the policy is attached to.

    

    

  IsAttachable -> (boolean)

    

    Specifies whether the policy can be attached to an IAM user, group, or role. 

    

    

  Description -> (string)

    

    A friendly description of the policy.

     

    This element is included in the response to the  get-policy operation. It is not included in the response to the  list-policies operation. 

    

    

  CreateDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

    

    

  UpdateDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

     

    When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created. 

    

    

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Versioning for Managed Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
