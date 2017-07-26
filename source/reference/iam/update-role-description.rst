[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-role-description:


***********************
update-role-description
***********************



===========
Description
===========



Modifies the description of a role.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateRoleDescription>`_


========
Synopsis
========

::

    update-role-description
  --role-name <value>
  --description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-name`` (string)


  The name of the role that you want to modify.

  

``--description`` (string)


  The new description that you want to apply to the specified role.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Role -> (structure)

  

  A structure that contains details about the modified role.

  

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

    

    

  

