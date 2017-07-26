[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms create-alias:


************
create-alias
************



===========
Description
===========



Creates a display name for a customer master key. An alias can be used to identify a key and should be unique. The console enforces a one-to-one mapping between the alias and a key. An alias name can contain only alphanumeric characters, forward slashes (/), underscores (_), and dashes (-). An alias must start with the word "alias" followed by a forward slash (alias/). An alias that begins with "aws" after the forward slash (alias/aws...) is reserved by Amazon Web Services (AWS).

 

The alias and the key it is mapped to must be in the same AWS account and the same region.

 

To map an alias to a different key, call  update-alias .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/CreateAlias>`_


========
Synopsis
========

::

    create-alias
  --alias-name <value>
  --target-key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alias-name`` (string)


  String that contains the display name. The name must start with the word "alias" followed by a forward slash (alias/). Aliases that begin with "alias/AWS" are reserved.

  

``--target-key-id`` (string)


  An identifier of the key for which you are creating the alias. This value cannot be another alias but can be a globally unique identifier or a fully specified ARN to a key.

   

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command creates an alias named ``example-alias`` for the customer master key (CMK) identified by key ID ``1234abcd-12ab-34cd-56ef-1234567890ab``.

.. code::

    aws kms create-alias --alias-name alias/example-alias --target-key-id 1234abcd-12ab-34cd-56ef-1234567890ab

Alias names must begin with ``alias/``. Do not use alias names that begin with ``alias/aws``; these are reserved for use by AWS.

======
Output
======

None