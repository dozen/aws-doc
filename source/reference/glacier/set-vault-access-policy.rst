[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier set-vault-access-policy:


***********************
set-vault-access-policy
***********************



===========
Description
===========



This operation configures an access policy for a vault and will overwrite an existing policy. To configure a vault access policy, send a PUT request to the ``access-policy`` subresource of the vault. An access policy is specific to a vault and is also called a vault subresource. You can set one access policy per vault and the policy can be up to 20 KB in size. For more information about vault access policies, see `Amazon Glacier Access Control with Vault Access Policies`_ . 



========
Synopsis
========

::

    set-vault-access-policy
  --account-id <value>
  --vault-name <value>
  [--policy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--policy`` (structure)


  The vault access policy as a JSON string.

  



Shorthand Syntax::

    Policy=string




JSON Syntax::

  {
    "Policy": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Amazon Glacier Access Control with Vault Access Policies: http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-access-policy.html
