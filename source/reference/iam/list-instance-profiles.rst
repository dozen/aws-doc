[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-instance-profiles:


**********************
list-instance-profiles
**********************



===========
Description
===========



Lists the instance profiles that have the specified path prefix. If there are none, the action returns an empty list. For more information about instance profiles, go to `About Instance Profiles`_ . 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-instance-profiles`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``InstanceProfiles``


========
Synopsis
========

::

    list-instance-profiles
  [--path-prefix <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--path-prefix`` (string)


  The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all instance profiles whose path starts with ``/application_abc/component_xyz/`` . 

   

  This parameter is optional. If it is not included, it defaults to a slash (/), listing all instance profiles. 

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To lists the instance profiles for the account**

The following ``list-instance-profiles`` command lists the instance profiles that are associated with the current account::

  aws iam list-instance-profiles

Output::

  {
    "InstanceProfiles": [
      {
        "InstanceProfileId": "AIPAIXEU4NUHUPEXAMPLE",
        "Roles": [
          {
            "AssumeRolePolicyDocument": {
              "Version": "2012-10-17",
              "Statement": [
                {
                  "Action": "sts:AssumeRole",
                  "Principal": {
                    "Service": "ec2.amazonaws.com"
                  },
                  "Effect": "Allow",
                  "Sid": ""
                }
              ]
            },
            "RoleId": "AROAJ52OTH4H7LEXAMPLE",
            "CreateDate": "2013-05-11T00:02:27Z",
            "RoleName": "example-role",
            "Path": "/",
            "Arn": "arn:aws:iam::123456789012:role/example-role"
          }
        ],
        "CreateDate": "2013-05-11T00:02:27Z",
        "InstanceProfileName": "ExampleInstanceProfile",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:instance-profile/ExampleInstanceProfile"
      },
      {
        "InstanceProfileId": "AIPAJVJVNRIQFREXAMPLE",
        "Roles": [
          {
            "AssumeRolePolicyDocument": {
              "Version": "2012-10-17",
              "Statement": [
                {
                  "Action": "sts:AssumeRole",
                  "Principal": {
                    "Service": "ec2.amazonaws.com"
                  },
                  "Effect": "Allow",
                  "Sid": ""
                }
              ]
            },
            "RoleId": "AROAINUBC5O7XLEXAMPLE",
            "CreateDate": "2013-01-09T06:33:26Z",
            "RoleName": "s3-test-role",
            "Path": "/",
            "Arn": "arn:aws:iam::123456789012:role/s3-test-role"
          }
        ],
        "CreateDate": "2013-06-12T23:52:02Z",
        "InstanceProfileName": "ExampleInstanceProfile2",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:instance-profile/ExampleInstanceProfile2"
      },
    ]
  }

For more information, see `Instance Profiles`_ in the *Using IAM* guide.

.. _`Instance Profiles`: http://docs.aws.amazon.com/IAM/latest/UserGuide/instance-profiles.html


======
Output
======

InstanceProfiles -> (list)

  

  A list of instance profiles.

  

  (structure)

    

    Contains information about an instance profile.

     

    This data type is used as a response element in the following actions:

     

     
    *  create-instance-profile   
     
    *  get-instance-profile   
     
    *  list-instance-profiles   
     
    *  list-instance-profiles-for-role   
     

    

    Path -> (string)

      

      The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    InstanceProfileName -> (string)

      

      The name identifying the instance profile.

      

      

    InstanceProfileId -> (string)

      

      The stable and unique string identifying the instance profile. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) specifying the instance profile. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    CreateDate -> (timestamp)

      

      The date when the instance profile was created.

      

      

    Roles -> (list)

      

      The role associated with the instance profile.

      

      (structure)

        

        Contains information about an IAM role.

         

        This data type is used as a response element in the following actions:

         

         
        *  create-role   
         
        *  get-role   
         
        *  list-roles   
         

        

        Path -> (string)

          

          The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

          

          

        RoleName -> (string)

          

          The friendly name that identifies the role.

          

          

        RoleId -> (string)

          

          The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

          

          

        Arn -> (string)

          

          The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

          

          

        CreateDate -> (timestamp)

          

          The date and time, in `ISO 8601 date-time format`_ , when the role was created.

          

          

        AssumeRolePolicyDocument -> (string)

          

          The policy that grants an entity permission to assume the role.

          

          

        

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _About Instance Profiles: http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html
