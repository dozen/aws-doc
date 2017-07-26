[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier complete-vault-lock:


*******************
complete-vault-lock
*******************



===========
Description
===========



This operation completes the vault locking process by transitioning the vault lock from the ``InProgress`` state to the ``Locked`` state, which causes the vault lock policy to become unchangeable. A vault lock is put into the ``InProgress`` state by calling  initiate-vault-lock . You can obtain the state of the vault lock by calling  get-vault-lock . For more information about the vault locking process, `Amazon Glacier Vault Lock <http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock.html>`_ . 

 

This operation is idempotent. This request is always successful if the vault lock is in the ``Locked`` state and the provided lock ID matches the lock ID originally used to lock the vault.

 

If an invalid lock ID is passed in the request when the vault lock is in the ``Locked`` state, the operation returns an ``AccessDeniedException`` error. If an invalid lock ID is passed in the request when the vault lock is in the ``InProgress`` state, the operation throws an ``InvalidParameter`` error.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/CompleteVaultLock>`_


========
Synopsis
========

::

    complete-vault-lock
  --account-id <value>
  --vault-name <value>
  --lock-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens ('-') in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--lock-id`` (string)


  The ``lockId`` value is the lock ID obtained from a  initiate-vault-lock request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None