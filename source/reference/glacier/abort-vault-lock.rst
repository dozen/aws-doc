[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier abort-vault-lock:


****************
abort-vault-lock
****************



===========
Description
===========



This operation aborts the vault locking process if the vault lock is not in the ``Locked`` state. If the vault lock is in the ``Locked`` state when this operation is requested, the operation returns an ``AccessDeniedException`` error. Aborting the vault locking process removes the vault lock policy from the specified vault. 

 

A vault lock is put into the ``InProgress`` state by calling  initiate-vault-lock . A vault lock is put into the ``Locked`` state by calling  complete-vault-lock . You can get the state of a vault lock by calling  get-vault-lock . For more information about the vault locking process, see `Amazon Glacier Vault Lock`_ . For more information about vault lock policies, see `Amazon Glacier Access Control with Vault Lock Policies`_ . 

 

This operation is idempotent. You can successfully invoke this operation multiple times, if the vault lock is in the ``InProgress`` state or if there is no policy associated with the vault.



========
Synopsis
========

::

    abort-vault-lock
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Amazon Glacier Vault Lock: http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock.html
.. _Amazon Glacier Access Control with Vault Lock Policies: http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock-policy.html
