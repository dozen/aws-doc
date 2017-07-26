[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot delete-policy:


*************
delete-policy
*************



===========
Description
===========



Deletes the specified policy.

 

A policy cannot be deleted if it has non-default versions or it is attached to any certificate.

 

To delete a policy, use the delete-policy-version API to delete all non-default versions of the policy; use the detach-principal-policy API to detach the policy from any certificate; and then use the delete-policy API to delete the policy.

 

When a policy is deleted using DeletePolicy, its default version is deleted with it.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DeletePolicy>`_


========
Synopsis
========

::

    delete-policy
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-name`` (string)


  The name of the policy to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None