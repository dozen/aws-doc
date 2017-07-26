[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot delete-policy:


*************
delete-policy
*************



===========
Description
===========



Deletes the specified policy.

 

A policy cannot be deleted if it has non-default versions and/or it is attached to any certificate.

 

To delete a policy, delete all non-default versions of the policy using the delete-policy-version API, detach the policy from any certificate using the detach-principal-policy API, and then use the delete-policy API to delete the policy.

 

When a policy is deleted using DeletePolicy, its default version is deleted with it.



========
Synopsis
========

::

    delete-policy
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None