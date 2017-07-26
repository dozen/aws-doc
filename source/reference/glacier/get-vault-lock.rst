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
 

 

A vault lock is put into the ``InProgress`` state by calling  initiate-vault-lock . A vault lock is put into the ``Locked`` state by calling  complete-vault-lock . You can abort the vault locking process by calling  abort-vault-lock . For more information about the vault locking process, `Amazon Glacier Vault Lock <http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock.html>`_ . 

 

If there is no vault lock policy set on the vault, the operation returns a ``404 Not found`` error. For more information about vault lock policies, `Amazon Glacier Access Control with Vault Lock Policies <http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock-policy.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/GetVaultLock>`_


========
Synopsis
========

::

    get-vault-lock
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

Policy -> (string)

  

  The vault lock policy as a JSON string, which uses "\" as an escape character.

  

  

State -> (string)

  

  The state of the vault lock. ``InProgress`` or ``Locked`` .

  

  

ExpirationDate -> (string)

  

  The UTC date and time at which the lock ID expires. This value can be ``null`` if the vault lock is in a ``Locked`` state.

  

  

CreationDate -> (string)

  

  The UTC date and time at which the vault lock was put into the ``InProgress`` state.

  

  

