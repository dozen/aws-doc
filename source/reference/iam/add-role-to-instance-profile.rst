[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam add-role-to-instance-profile:


****************************
add-role-to-instance-profile
****************************



===========
Description
===========



Adds the specified IAM role to the specified instance profile. An instance profile can contain only one role, and this limit cannot be increased.

 

.. note::

   

  The caller of this API must be granted the ``PassRole`` permission on the IAM role by a permission policy.

   

 

For more information about roles, go to `Working with Roles <http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html>`_ . For more information about instance profiles, go to `About Instance Profiles <http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/AddRoleToInstanceProfile>`_


========
Synopsis
========

::

    add-role-to-instance-profile
  --instance-profile-name <value>
  --role-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to update.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--role-name`` (string)


  The name of the role to add.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: _+=,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add a role to an instance profile**

The following ``add-role-to-instance-profile`` command adds the role named ``S3Access`` to the instance profile named ``Webserver``::

  aws iam add-role-to-instance-profile --role-name S3Access --instance-profile-name Webserver

To create an instance profile, use the ``create-instance-profile`` command.

For more information, see `Using IAM Roles to Delegate Permissions to Applications that Run on Amazon EC2`_ in the *Using IAM* guide.

.. _`Using IAM Roles to Delegate Permissions to Applications that Run on Amazon EC2`: http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-usingrole-ec2instance.html

======
Output
======

None