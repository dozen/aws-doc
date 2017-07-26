[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations delete-policy:


*************
delete-policy
*************



===========
Description
===========



Deletes the specified policy from your organization. Before you perform this operation, you must first detach the policy from all OUs, roots, and accounts.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DeletePolicy>`_


========
Synopsis
========

::

    delete-policy
  --policy-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-id`` (string)


  The unique identifier (ID) of the policy that you want to delete. You can get the ID from the  list-policies or  list-policies-for-target operations.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a policy ID string requires "p-" followed by from 8 to 128 lower-case letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a policy**

The following example shows how to delete a policy from an organization. The example assumes that you previously detached the policy from all entities.

Command::

  aws organizations delete-policy --policy-id p-examplepolicyid111

======
Output
======

None