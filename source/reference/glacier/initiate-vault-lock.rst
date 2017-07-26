[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier initiate-vault-lock:


*******************
initiate-vault-lock
*******************



===========
Description
===========



This operation initiates the vault locking process by doing the following:

 

 
* Installing a vault lock policy on the specified vault. 
 
* Setting the lock state of vault lock to ``InProgress`` . 
 
* Returning a lock ID, which is used to complete the vault locking process. 
 

 

You can set one vault lock policy for each vault and this policy can be up to 20 KB in size. For more information about vault lock policies, see `Amazon Glacier Access Control with Vault Lock Policies <http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock-policy.html>`_ . 

 

You must complete the vault locking process within 24 hours after the vault lock enters the ``InProgress`` state. After the 24 hour window ends, the lock ID expires, the vault automatically exits the ``InProgress`` state, and the vault lock policy is removed from the vault. You call  complete-vault-lock to complete the vault locking process by setting the state of the vault lock to ``Locked`` . 

 

After a vault lock is in the ``Locked`` state, you cannot initiate a new vault lock for the vault.

 

You can abort the vault locking process by calling  abort-vault-lock . You can get the state of the vault lock by calling  get-vault-lock . For more information about the vault locking process, `Amazon Glacier Vault Lock <http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock.html>`_ .

 

If this operation is called when the vault lock is in the ``InProgress`` state, the operation returns an ``AccessDeniedException`` error. When the vault lock is in the ``InProgress`` state you must call  abort-vault-lock before you can initiate a new vault lock policy. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/InitiateVaultLock>`_


========
Synopsis
========

::

    initiate-vault-lock
  --account-id <value>
  --vault-name <value>
  [--policy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens ('-') in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--policy`` (structure)


  The vault lock policy as a JSON string, which uses "\" as an escape character.

  



Shorthand Syntax::

    Policy=string




JSON Syntax::

  {
    "Policy": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

lockId -> (string)

  

  The lock ID, which is used to complete the vault locking process.

  

  

