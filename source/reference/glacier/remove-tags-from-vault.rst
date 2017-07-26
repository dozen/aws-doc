[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier remove-tags-from-vault:


**********************
remove-tags-from-vault
**********************



===========
Description
===========



This operation removes one or more tags from the set of tags attached to a vault. For more information about tags, see `Tagging Amazon Glacier Resources`_ . This operation is idempotent. The operation will be successful, even if there are no tags attached to the vault. 



========
Synopsis
========

::

    remove-tags-from-vault
  --account-id <value>
  --vault-name <value>
  [--tag-keys <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--tag-keys`` (list)


  A list of tag keys. Each corresponding tag is removed from the vault.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command removes a tag with the key ``date`` from a vault named ``my-vault``::

  aws glacier remove-tags-from-vault --account-id - --vault-name my-vault --tag-keys date

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.


======
Output
======

None

.. _Tagging Amazon Glacier Resources: http://docs.aws.amazon.com/amazonglacier/latest/dev/tagging.html
