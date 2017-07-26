[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-role:


***********
delete-role
***********



===========
Description
===========



Deletes the specified role. The role must not have any policies attached. For more information about roles, go to `Working with Roles`_ . 

 

.. warning::

  Make sure you do not have any Amazon EC2 instances running with the role you are about to delete. Deleting a role or instance profile that is associated with a running instance will break any applications running on the instance. 



========
Synopsis
========

::

    delete-role
  --role-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-name`` (string)


  The name of the role to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an IAM role**

The following ``delete-role`` command removes the role named ``Test-Role``::

  aws iam delete-role --role-name Test-Role

Before you can delete a role, you must remove the role from any instance profile (``remove-role-from-instance-policy``) and delete any policies that are attached to the role (``delete-role-policy``).

For more information, see `Creating a Role`_ and `Instance Profiles`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html
.. _Instance Profiles: http://docs.aws.amazon.com/IAM/latest/UserGuide/instance-profiles.html




======
Output
======

None

.. _Working with Roles: http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html
