[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms update-alias:


************
update-alias
************



===========
Description
===========



Updates an alias to map it to a different key.

 

An alias is not a property of a key. Therefore, an alias can be mapped to and unmapped from an existing key without changing the properties of the key.

 

An alias name can contain only alphanumeric characters, forward slashes (/), underscores (_), and dashes (-). An alias must start with the word "alias" followed by a forward slash (alias/). An alias that begins with "aws" after the forward slash (alias/aws...) is reserved by Amazon Web Services (AWS).

 

The alias and the key it is mapped to must be in the same AWS account and the same region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/UpdateAlias>`_


========
Synopsis
========

::

    update-alias
  --alias-name <value>
  --target-key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alias-name`` (string)


  String that contains the name of the alias to be modified. The name must start with the word "alias" followed by a forward slash (alias/). Aliases that begin with "alias/aws" are reserved.

  

``--target-key-id`` (string)


  Unique identifier of the customer master key to be mapped to the alias. This value can be a globally unique identifier or the fully specified ARN of a key.

   

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
   

   

  You can call  list-aliases to verify that the alias is mapped to the correct ``TargetKeyId`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None