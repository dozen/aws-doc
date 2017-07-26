[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam remove-role-from-instance-profile:


*********************************
remove-role-from-instance-profile
*********************************



===========
Description
===========



Removes the specified role from the specified instance profile.

 

.. warning::

  Make sure you do not have any Amazon EC2 instances running with the role you are about to remove from the instance profile. Removing a role from an instance profile that is associated with a running instance will break any applications running on the instance. 

 

For more information about roles, go to `Working with Roles`_ . For more information about instance profiles, go to `About Instance Profiles`_ . 



========
Synopsis
========

::

    remove-role-from-instance-profile
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


  The name of the role to remove.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove a role from an instance profile**

The following ``remove-role-from-instance-profile`` command removes the role named ``Test-Role`` from the instance
profile named ``ExampleInstanceProfile``::

  aws iam remove-role-from-instance-profile --instance-profile-name ExampleInstanceProfile --role-name Test-Role

For more information, see `Instance Profiles`_ in the *Using IAM* guide.

.. _`Instance Profiles`: http://docs.aws.amazon.com/IAM/latest/UserGuide/instance-profiles.html



======
Output
======

None

.. _Working with Roles: http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html
.. _About Instance Profiles: http://docs.aws.amazon.com/IAM/latest/UserGuide/AboutInstanceProfiles.html
