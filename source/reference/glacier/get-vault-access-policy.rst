[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier get-vault-access-policy:


***********************
get-vault-access-policy
***********************



===========
Description
===========



This operation retrieves the ``access-policy`` subresource set on the vault; for more information on setting this subresource, see `Set Vault Access Policy (PUT access-policy)`_ . If there is no access policy set on the vault, the operation returns a ``404 Not found`` error. For more information about vault access policies, see `Amazon Glacier Access Control with Vault Access Policies`_ .



========
Synopsis
========

::

    get-vault-access-policy
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

policy -> (structure)

  

  Contains the returned vault access policy as a JSON string.

  

  Policy -> (string)

    

    The vault access policy.

    

    

  



.. _Set Vault Access Policy (PUT access-policy): http://docs.aws.amazon.com/amazonglacier/latest/dev/api-SetVaultAccessPolicy.html
.. _Amazon Glacier Access Control with Vault Access Policies: http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-access-policy.html
