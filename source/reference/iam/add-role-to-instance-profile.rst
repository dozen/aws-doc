[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam add-role-to-instance-profile:


****************************
add-role-to-instance-profile
****************************



===========
Description
===========



Adds the specified role to the specified instance profile. For more information about roles, go to `Working with Roles`_ . For more information about instance profiles, go to `About Instance Profiles`_ . 



========
Synopsis
========

::

    add-role-to-instance-profile
  --instance-profile-name <value>
  --role-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to update.

  

``--role-name`` (string)


  The name of the role to add.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Working with Roles: http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html
.. _About Instance Profiles: http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html
