[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier add-tags-to-vault:


*****************
add-tags-to-vault
*****************



===========
Description
===========



This operation adds the specified tags to a vault. Each tag is composed of a key and a value. Each vault can have up to 10 tags. If your request would cause the tag limit for the vault to be exceeded, the operation throws the ``LimitExceededException`` error. If a tag already exists on the vault under a specified key, the existing key value will be overwritten. For more information about tags, see `Tagging Amazon Glacier Resources`_ . 



========
Synopsis
========

::

    add-tags-to-vault
  --account-id <value>
  --vault-name <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--tags`` (map)


  The tags to add to the vault. Each tag is composed of a key and a value. The value can be an empty string.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command adds two tags to a vault named ``my-vault``::

  aws glacier add-tags-to-vault --account-id - --vault-name my-vault --tags id=1234,date=july2015

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.


======
Output
======

None

.. _Tagging Amazon Glacier Resources: http://docs.aws.amazon.com/amazonglacier/latest/dev/tagging.html
