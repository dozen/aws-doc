[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-instance-profile:


***********************
create-instance-profile
***********************



===========
Description
===========



Creates a new instance profile. For information about instance profiles, go to `About Instance Profiles <http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html>`_ .

 

For information about the number of instance profiles you can create, see `Limitations on IAM Entities <http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/CreateInstanceProfile>`_


========
Synopsis
========

::

    create-instance-profile
  --instance-profile-name <value>
  [--path <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to create.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--path`` (string)


  The path to the instance profile. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *IAM User Guide* .

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

   

  This paramater allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  A structure containing details about the new instance profile.

  

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

        

        

      

    

  

