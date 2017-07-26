[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-instance-profile:


***********************
create-instance-profile
***********************



===========
Description
===========



Creates a new instance profile. For information about instance profiles, go to `About Instance Profiles`_ . 

 

For information about the number of instance profiles you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    create-instance-profile
  --instance-profile-name <value>
  [--path <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to create.

  

``--path`` (string)


  The path to the instance profile. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an instance profile**

The following ``create-instance-profile`` command creates an instance profile named ``Webserver``::

  aws iam create-instance-profile --instance-profile-name Webserver

Output::

  {
      "InstanceProfile": {
          "InstanceProfileId": "AIPAJMBYC7DLSPEXAMPLE",
          "Roles": [],
          "CreateDate": "2015-03-09T20:33:19.626Z",
          "InstanceProfileName": "Webserver",
          "Path": "/",
          "Arn": "arn:aws:iam::123456789012:instance-profile/Webserver"
      }
  }

To add a role to an instance profile, use the ``add-role-to-instance-profile`` command.

For more information, see `Using IAM Roles to Delegate Permissions to Applications that Run on Amazon EC2`_ in the *Using IAM* guide.

.. _`Using IAM Roles to Delegate Permissions to Applications that Run on Amazon EC2`: http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-usingrole-ec2instance.html

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

        

        

      

    

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _About Instance Profiles: http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html
.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
