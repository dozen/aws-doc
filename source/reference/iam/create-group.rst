[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-group:


************
create-group
************



===========
Description
===========



Creates a new group.

 

For information about the number of groups you can create, see `Limitations on IAM Entities`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    create-group
  [--path <value>]
  --group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--path`` (string)


  The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

  

``--group-name`` (string)


  The name of the group to create. Do not include the path in this value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an IAM group**

The following ``create-group`` command creates an IAM group named ``Admins``::

  aws iam create-group --group-name Admins

Output::

  {
      "Group": {
          "Path": "/",
          "CreateDate": "2015-03-09T20:30:24.940Z",
          "GroupId": "AIDGPMS9RO4H3FEXAMPLE",
          "Arn": "arn:aws:iam::123456789012:group/Admins",
          "GroupName": "Admins"
      }
  }

For more information, see `Creating IAM Groups`_ in the *Using IAM* guide.

.. _`Creating IAM Groups`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_CreatingAndListingGroups.html

======
Output
======

Group -> (structure)

  

  Information about the group.

  

  Path -> (string)

    

    The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

    

    

  GroupName -> (string)

    

    The friendly name that identifies the group.

    

    

  GroupId -> (string)

    

    The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

    

    

  CreateDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format`_ , when the group was created.

    

    

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
