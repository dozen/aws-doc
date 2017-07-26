[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier get-vault-lock:


**************
get-vault-lock
**************



===========
Description
===========



This operation retrieves the following attributes from the ``lock-policy`` subresource set on the specified vault: 

 
* The vault lock policy set on the vault. 
 
* The state of the vault lock, which is either ``InProgess`` or ``Locked`` . 
 
* When the lock ID expires. The lock ID is used to complete the vault locking process. 
 
* When the vault lock was initiated and put into the ``InProgress`` state. 
 

 

 

A vault lock is put into the ``InProgress`` state by calling  initiate-vault-lock . A vault lock is put into the ``Locked`` state by calling  complete-vault-lock . You can abort the vault locking process by calling  abort-vault-lock . For more information about the vault locking process, `Amazon Glacier Vault Lock`_ . 

 

If there is no vault lock policy set on the vault, the operation returns a ``404 Not found`` error. For more information about vault lock policies, `Amazon Glacier Access Control with Vault Lock Policies`_ . 



========
Synopsis
========

::

    get-vault-lock
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

Policy -> (string)

  

  The vault lock policy as a JSON string, which uses "\" as an escape character.

  

  

State -> (string)

  

  The state of the vault lock. ``InProgress`` or ``Locked`` .

  

  

ExpirationDate -> (string)

  

  The UTC date and time at which the lock ID expires. This value can be ``null`` if the vault lock is in a ``Locked`` state.

  

  

CreationDate -> (string)

  

  The UTC date and time at which the vault lock was put into the ``InProgress`` state.

  

  



.. _Amazon Glacier Vault Lock: http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock.html
.. _Amazon Glacier Access Control with Vault Lock Policies: http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock-policy.html
