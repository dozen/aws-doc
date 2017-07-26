[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-instance-profile:


********************
get-instance-profile
********************



===========
Description
===========



Retrieves information about the specified instance profile, including the instance profile's path, GUID, ARN, and role. For more information about instance profiles, go to `About Instance Profiles`_ . For more information about ARNs, go to `ARNs`_ . 



========
Synopsis
========

::

    get-instance-profile
  --instance-profile-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about an instance profile**

The following ``get-instance-profile`` command gets information about the instance profile named ``ExampleInstanceProfile``::

  aws iam get-instance-profile --instance-profile-name ExampleInstanceProfile

Output::

  {
      "InstanceProfile": {
          "InstanceProfileId": "AID2MAB8DPLSRHEXAMPLE",
          "Roles": [
              {
                  "AssumeRolePolicyDocument": "<URL-encoded-JSON>",
                  "RoleId": "AIDGPMS9RO4H3FEXAMPLE",
                  "CreateDate": "2013-01-09T06:33:26Z",
                  "RoleName": "Test-Role",
                  "Path": "/",
                  "Arn": "arn:aws:iam::336924118301:role/Test-Role"
              }
          ],
          "CreateDate": "2013-06-12T23:52:02Z",
          "InstanceProfileName": "ExampleInstanceProfile",
          "Path": "/",
          "Arn": "arn:aws:iam::336924118301:instance-profile/ExampleInstanceProfile"
      }
  }

For more information, see `Instance Profiles`_ in the *Using IAM* guide.

.. _`Instance Profiles`: http://docs.aws.amazon.com/IAM/latest/UserGuide/instance-profiles.html


======
Output
======

InstanceProfile -> (structure)

  

  Information about the instance profile.

  

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

        

        

      

    

  



.. _ARNs: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html#Identifiers_ARNs
.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _About Instance Profiles: http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html
