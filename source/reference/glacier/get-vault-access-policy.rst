[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier get-vault-access-policy:


***********************
get-vault-access-policy
***********************



===========
Description
===========



This operation retrieves the ``access-policy`` subresource set on the vault; for more information on setting this subresource, see `Set Vault Access Policy (PUT access-policy) <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-SetVaultAccessPolicy.html>`_ . If there is no access policy set on the vault, the operation returns a ``404 Not found`` error. For more information about vault access policies, see `Amazon Glacier Access Control with Vault Access Policies <http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-access-policy.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/GetVaultAccessPolicy>`_


========
Synopsis
========

::

    get-vault-access-policy
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens ('-') in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

policy -> (structure)

  

  Contains the returned vault access policy as a JSON string.

  

  Policy -> (string)

    

    The vault access policy.

    

    

  

