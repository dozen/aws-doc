[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-account-authorization-details:


*********************************
get-account-authorization-details
*********************************



===========
Description
===========



Retrieves information about all IAM users, groups, roles, and policies in your AWS account, including their relationships to one another. Use this API to obtain a snapshot of the configuration of IAM permissions (users, groups, roles, and policies) in your account.

 

You can optionally filter the results using the ``Filter`` parameter. You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetAccountAuthorizationDetails>`_


``get-account-authorization-details`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``UserDetailList``, ``GroupDetailList``, ``RoleDetailList``, ``Policies``


========
Synopsis
========

::

    get-account-authorization-details
  [--filter <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (list)


  A list of entity types used to filter the results. Only the entities that match the types you specify are included in the output. Use the value ``LocalManagedPolicy`` to include customer managed policies.

   

  The format for this parameter is a comma-separated (if more than one) list of strings. Each string value in the list must be one of the valid values listed below.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    User
    Role
    Group
    LocalManagedPolicy
    AWSManagedPolicy





``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following ``get-account-authorization-details`` command returns information about all IAM users, groups, roles, and policies in the AWS account::

  aws iam get-account-authorization-details

Output::

  {
    "RoleDetailList": [
      {
        "AssumeRolePolicyDocument": {
          "Version": "2012-10-17",
          "Statement": [
            {
              "Sid": "",
              "Effect": "Allow",
              "Principal": {
                "Service": "ec2.amazonaws.com"
              },
              "Action": "sts:AssumeRole"
            }
          ]
        },
        "RoleId": "AROAFP4BKI7Y7TEXAMPLE",
        "CreateDate": "2014-07-30T17:09:20Z",
        "InstanceProfileList": [
          {
            "InstanceProfileId": "AIPAFFYRBHWXW2EXAMPLE",
            "Roles": [
              {
                "AssumeRolePolicyDocument": {
                  "Version":"2012-10-17",
                  "Statement": [
                    {
                      "Sid":"",
                      "Effect":"Allow",
                      "Principal": {
                        "Service":"ec2.amazonaws.com"
                      },
                      "Action":"sts:AssumeRole"
                    }
                  ]
                },
                "RoleId": "AROAFP4BKI7Y7TEXAMPLE",
                "CreateDate": "2014-07-30T17:09:20Z",
                "RoleName": "EC2role",
                "Path": "/",
                "Arn": "arn:aws:iam::123456789012:role/EC2role"
              }
            ],
            "CreateDate": "2014-07-30T17:09:20Z",
            "InstanceProfileName": "EC2role",
            "Path": "/",
            "Arn": "arn:aws:iam::123456789012:instance-profile/EC2role"
          }
        ],
        "RoleName": "EC2role",
        "Path": "/",
        "AttachedManagedPolicies": [
          {
            "PolicyName": "AmazonS3FullAccess",
            "PolicyArn": "arn:aws:iam::aws:policy/AmazonS3FullAccess"
          },
          {
            "PolicyName": "AmazonDynamoDBFullAccess",
            "PolicyArn": "arn:aws:iam::aws:policy/AmazonDynamoDBFullAccess"
          }
        ],
        "RolePolicyList": [],
        "Arn": "arn:aws:iam::123456789012:role/EC2role"
      }],
    "GroupDetailList": [
      {
        "GroupId": "AIDACKCEVSQ6C7EXAMPLE",
        "AttachedManagedPolicies": {
          "PolicyName": "AdministratorAccess",
          "PolicyArn": "arn:aws:iam::aws:policy/AdministratorAccess"
        },
        "GroupName": "Admins",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:group/Admins",
        "CreateDate": "2013-10-14T18:32:24Z",
        "GroupPolicyList": []
      },
      {
        "GroupId": "AIDACKCEVSQ6C8EXAMPLE",
        "AttachedManagedPolicies": {
          "PolicyName": "PowerUserAccess",
          "PolicyArn": "arn:aws:iam::aws:policy/PowerUserAccess"
        },
        "GroupName": "Dev",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:group/Dev",
        "CreateDate": "2013-10-14T18:33:55Z",
        "GroupPolicyList": []
      },
      {
        "GroupId": "AIDACKCEVSQ6C9EXAMPLE",
        "AttachedManagedPolicies": [],
        "GroupName": "Finance",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:group/Finance",
        "CreateDate": "2013-10-14T18:57:48Z",
        "GroupPolicyList": [
          {
            "PolicyName": "policygen-201310141157",
            "PolicyDocument": {
              "Version":"2012-10-17",
              "Statement": [
                {
                  "Action": "aws-portal:*",
                  "Sid":"Stmt1381777017000",
                  "Resource": "*",
                  "Effect":"Allow"
                }
              ]
            }
          }
        ]
      }],
    "UserDetailList": [
      {
        "UserName": "Alice",
        "GroupList": [
          "Admins"
        ],
        "CreateDate": "2013-10-14T18:32:24Z",
        "UserId": "AIDACKCEVSQ6C2EXAMPLE",
        "UserPolicyList": [],
        "Path": "/",
        "AttachedManagedPolicies": [],
        "Arn": "arn:aws:iam::123456789012:user/Alice"
      },
      {
        "UserName": "Bob",
        "GroupList": [
          "Admins"
        ],
        "CreateDate": "2013-10-14T18:32:25Z",
        "UserId": "AIDACKCEVSQ6C3EXAMPLE",
        "UserPolicyList": [
          {
            "PolicyName": "DenyBillingAndIAMPolicy",
            "PolicyDocument": {
              "Version":"2012-10-17",
              "Statement": {
                "Effect":"Deny",
                "Action": [
                  "aws-portal:*",
                  "iam:*"
                ],
                "Resource":"*"
              }
            }
          }
        ],
        "Path": "/",
        "AttachedManagedPolicies": [],
        "Arn": "arn:aws:iam::123456789012:user/Bob"
      },
      {
        "UserName": "Charlie",
        "GroupList": [
          "Dev"
        ],
        "CreateDate": "2013-10-14T18:33:56Z",
        "UserId": "AIDACKCEVSQ6C4EXAMPLE",
        "UserPolicyList": [],
        "Path": "/",
        "AttachedManagedPolicies": [],
        "Arn": "arn:aws:iam::123456789012:user/Charlie"
      }],
    "Policies": [
      {
        "PolicyName": "create-update-delete-set-managed-policies",
        "CreateDate": "2015-02-06T19:58:34Z",
        "AttachmentCount": 1,
        "IsAttachable": true,
        "PolicyId": "ANPAJ2UCCR6DPCEXAMPLE",
        "DefaultVersionId": "v1",
        "PolicyVersionList": [
          {
            "CreateDate": "2015-02-06T19:58:34Z",
            "VersionId": "v1",
            "Document": {
              "Version":"2012-10-17",
              "Statement": {
                "Effect":"Allow",
                "Action": [
                  "iam:CreatePolicy",
                  "iam:CreatePolicyVersion",
                  "iam:DeletePolicy",
                  "iam:DeletePolicyVersion",
                  "iam:GetPolicy",
                  "iam:GetPolicyVersion",
                  "iam:ListPolicies",
                  "iam:ListPolicyVersions",
                  "iam:SetDefaultPolicyVersion"
                ], 
                "Resource": "*"
              }
            },
            "IsDefaultVersion": true
          }
        ],
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:policy/create-update-delete-set-managed-policies",
        "UpdateDate": "2015-02-06T19:58:34Z"
      },
      {
        "PolicyName": "S3-read-only-specific-bucket",
        "CreateDate": "2015-01-21T21:39:41Z",
        "AttachmentCount": 1,
        "IsAttachable": true,
        "PolicyId": "ANPAJ4AE5446DAEXAMPLE",
        "DefaultVersionId": "v1",
        "PolicyVersionList": [
          {
            "CreateDate": "2015-01-21T21:39:41Z",
            "VersionId": "v1",
            "Document": {
              "Version":"2012-10-17",
              "Statement": [
                {
                  "Effect":"Allow",
                  "Action": [
                    "s3:Get*",
                    "s3:List*"
                  ],
                  "Resource": [
                    "arn:aws:s3:::example-bucket",
                    "arn:aws:s3:::example-bucket/*"
                  ]
                }
              ]
            },
            "IsDefaultVersion": true
          }
        ],  
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:policy/S3-read-only-specific-bucket",
        "UpdateDate": "2015-01-21T23:39:41Z"
      },
      {
        "PolicyName": "AmazonEC2FullAccess",
        "CreateDate": "2015-02-06T18:40:15Z",
        "AttachmentCount": 1,
        "IsAttachable": true,
        "PolicyId": "ANPAE3QWE5YT46TQ34WLG",
        "DefaultVersionId": "v1",
        "PolicyVersionList": [
          {
            "CreateDate": "2014-10-30T20:59:46Z",
            "VersionId": "v1",
            "Document": {
              "Version":"2012-10-17",
              "Statement": [
                {
                  "Action":"ec2:*",
                  "Effect":"Allow",
                  "Resource":"*"
                },
                {
                  "Effect":"Allow",
                  "Action":"elasticloadbalancing:*",
                  "Resource":"*"
                },
                {
                  "Effect":"Allow",
                  "Action":"cloudwatch:*",
                  "Resource":"*"
                },
                {
                  "Effect":"Allow",
                  "Action":"autoscaling:*",
                  "Resource":"*"
                }
              ]
            },
            "IsDefaultVersion": true
          }
        ],
        "Path": "/",
        "Arn": "arn:aws:iam::aws:policy/AmazonEC2FullAccess",
        "UpdateDate": "2015-02-06T18:40:15Z"
      }],
    "Marker": "EXAMPLEkakv9BCuUNFDtxWSyfzetYwEx2ADc8dnzfvERF5S6YMvXKx41t6gCl/eeaCX3Jo94/bKqezEAg8TEVS99EKFLxm3jtbpl25FDWEXAMPLE",
    "IsTruncated": true
  }

======
Output
======

UserDetailList -> (list)

  

  A list containing information about IAM users.

  

  (structure)

    

    Contains information about an IAM user, including all the user's policies and all the IAM groups the user is in.

     

    This data type is used as a response element in the  get-account-authorization-details action.

    

    Path -> (string)

      

      The path to the user. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    UserName -> (string)

      

      The friendly name identifying the user.

      

      

    UserId -> (string)

      

      The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

       

      For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the user was created.

      

      

    UserPolicyList -> (list)

      

      A list of the inline policies embedded in the user.

      

      (structure)

        

        Contains information about an IAM policy, including the policy document.

         

        This data type is used as a response element in the  get-account-authorization-details action.

        

        PolicyName -> (string)

          

          The name of the policy.

          

          

        PolicyDocument -> (string)

          

          The policy document.

          

          

        

      

    GroupList -> (list)

      

      A list of IAM groups that the user is in.

      

      (string)

        

        

      

    AttachedManagedPolicies -> (list)

      

      A list of the managed policies attached to the user.

      

      (structure)

        

        Contains information about an attached policy.

         

        An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  list-attached-group-policies ,  list-attached-role-policies ,  list-attached-user-policies , and  get-account-authorization-details actions. 

         

        For more information about managed policies, refer to `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *Using IAM* guide. 

        

        PolicyName -> (string)

          

          The friendly name of the attached policy.

          

          

        PolicyArn -> (string)

          

          The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

           

          For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

          

          

        

      

    

  

GroupDetailList -> (list)

  

  A list containing information about IAM groups.

  

  (structure)

    

    Contains information about an IAM group, including all of the group's policies.

     

    This data type is used as a response element in the  get-account-authorization-details action.

    

    Path -> (string)

      

      The path to the group. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    GroupName -> (string)

      

      The friendly name that identifies the group.

      

      

    GroupId -> (string)

      

      The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

       

      For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the group was created.

      

      

    GroupPolicyList -> (list)

      

      A list of the inline policies embedded in the group.

      

      (structure)

        

        Contains information about an IAM policy, including the policy document.

         

        This data type is used as a response element in the  get-account-authorization-details action.

        

        PolicyName -> (string)

          

          The name of the policy.

          

          

        PolicyDocument -> (string)

          

          The policy document.

          

          

        

      

    AttachedManagedPolicies -> (list)

      

      A list of the managed policies attached to the group.

      

      (structure)

        

        Contains information about an attached policy.

         

        An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  list-attached-group-policies ,  list-attached-role-policies ,  list-attached-user-policies , and  get-account-authorization-details actions. 

         

        For more information about managed policies, refer to `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *Using IAM* guide. 

        

        PolicyName -> (string)

          

          The friendly name of the attached policy.

          

          

        PolicyArn -> (string)

          

          The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

           

          For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

          

          

        

      

    

  

RoleDetailList -> (list)

  

  A list containing information about IAM roles.

  

  (structure)

    

    Contains information about an IAM role, including all of the role's policies.

     

    This data type is used as a response element in the  get-account-authorization-details action.

    

    Path -> (string)

      

      The path to the role. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    RoleName -> (string)

      

      The friendly name that identifies the role.

      

      

    RoleId -> (string)

      

      The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

       

      For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the role was created.

      

      

    AssumeRolePolicyDocument -> (string)

      

      The trust policy that grants permission to assume the role.

      

      

    InstanceProfileList -> (list)

      

      A list of instance profiles that contain this role.

      

      (structure)

        

        Contains information about an instance profile.

         

        This data type is used as a response element in the following actions:

         

         
        *  create-instance-profile   
         
        *  get-instance-profile   
         
        *  list-instance-profiles   
         
        *  list-instance-profiles-for-role   
         

        

        Path -> (string)

          

          The path to the instance profile. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

          

          

        InstanceProfileName -> (string)

          

          The name identifying the instance profile.

          

          

        InstanceProfileId -> (string)

          

          The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

          

          

        Arn -> (string)

          

          The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

          

          

        CreateDate -> (timestamp)

          

          The date when the instance profile was created.

          

          

        Roles -> (list)

          

          The role associated with the instance profile.

          

          (structure)

            

            Contains information about an IAM role. This structure is returned as a response element in several APIs that interact with roles.

            

            Path -> (string)

              

              The path to the role. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

              

              

            RoleName -> (string)

              

              The friendly name that identifies the role.

              

              

            RoleId -> (string)

              

              The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

              

              

            Arn -> (string)

              

              The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *IAM User Guide* guide. 

              

              

            CreateDate -> (timestamp)

              

              The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the role was created.

              

              

            AssumeRolePolicyDocument -> (string)

              

              The policy that grants an entity permission to assume the role.

              

              

            Description -> (string)

              

              A description of the role that you provide.

              

              

            

          

        

      

    RolePolicyList -> (list)

      

      A list of inline policies embedded in the role. These policies are the role's access (permissions) policies.

      

      (structure)

        

        Contains information about an IAM policy, including the policy document.

         

        This data type is used as a response element in the  get-account-authorization-details action.

        

        PolicyName -> (string)

          

          The name of the policy.

          

          

        PolicyDocument -> (string)

          

          The policy document.

          

          

        

      

    AttachedManagedPolicies -> (list)

      

      A list of managed policies attached to the role. These policies are the role's access (permissions) policies.

      

      (structure)

        

        Contains information about an attached policy.

         

        An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  list-attached-group-policies ,  list-attached-role-policies ,  list-attached-user-policies , and  get-account-authorization-details actions. 

         

        For more information about managed policies, refer to `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *Using IAM* guide. 

        

        PolicyName -> (string)

          

          The friendly name of the attached policy.

          

          

        PolicyArn -> (string)

          

          The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

           

          For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

          

          

        

      

    

  

Policies -> (list)

  

  A list containing information about managed policies.

  

  (structure)

    

    Contains information about a managed policy, including the policy's ARN, versions, and the number of principal entities (users, groups, and roles) that the policy is attached to.

     

    This data type is used as a response element in the  get-account-authorization-details action.

     

    For more information about managed policies, see `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *Using IAM* guide. 

    

    PolicyName -> (string)

      

      The friendly name (not ARN) identifying the policy.

      

      

    PolicyId -> (string)

      

      The stable and unique string identifying the policy.

       

      For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

       

      For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

      

      

    Path -> (string)

      

      The path to the policy.

       

      For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

      

      

    DefaultVersionId -> (string)

      

      The identifier for the version of the policy that is set as the default (operative) version.

       

      For more information about policy versions, see `Versioning for Managed Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html>`_ in the *Using IAM* guide. 

      

      

    AttachmentCount -> (integer)

      

      The number of principal entities (users, groups, and roles) that the policy is attached to.

      

      

    IsAttachable -> (boolean)

      

      Specifies whether the policy can be attached to an IAM user, group, or role.

      

      

    Description -> (string)

      

      A friendly description of the policy.

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the policy was created.

      

      

    UpdateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the policy was last updated.

       

      When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created.

      

      

    PolicyVersionList -> (list)

      

      A list containing information about the versions of the policy.

      

      (structure)

        

        Contains information about a version of a managed policy.

         

        This data type is used as a response element in the  create-policy-version ,  get-policy-version ,  list-policy-versions , and  get-account-authorization-details actions. 

         

        For more information about managed policies, refer to `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *Using IAM* guide. 

        

        Document -> (string)

          

          The policy document.

           

          The policy document is returned in the response to the  get-policy-version and  get-account-authorization-details operations. It is not returned in the response to the  create-policy-version or  list-policy-versions operations. 

          

          

        VersionId -> (string)

          

          The identifier for the policy version.

           

          Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

          

          

        IsDefaultVersion -> (boolean)

          

          Specifies whether the policy version is set as the policy's default version.

          

          

        CreateDate -> (timestamp)

          

          The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the policy version was created.

          

          

        

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

