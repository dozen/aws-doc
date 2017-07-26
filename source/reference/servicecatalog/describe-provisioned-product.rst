[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-provisioned-product:


****************************
describe-provisioned-product
****************************



===========
Description
===========



Retrieve detailed information about the provisioned product.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeProvisionedProduct>`_


========
Synopsis
========

::

    describe-provisioned-product
  [--accept-language <value>]
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--accept-language`` (string)


  The language code to use for this operation. Supported language codes are as follows:

   

  "en" (English)

   

  "jp" (Japanese)

   

  "zh" (Chinese)

   

  If no code is specified, "en" is used as the default.

  

``--id`` (string)


  The provisioned product identifier.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProvisionedProductDetail -> (structure)

  

  Detailed provisioned product information.

  

  Name -> (string)

    

    The user-friendly name of the ProvisionedProduct object.

    

    

  Arn -> (string)

    

    The ARN associated with the ProvisionedProduct object.

    

    

  Type -> (string)

    

    The type of the ProvisionedProduct object.

    

    

  Id -> (string)

    

    The identifier of the ProvisionedProduct object.

    

    

  Status -> (string)

    

    The current status of the ProvisionedProduct.

     

     ``AVAILABLE`` - Stable state, ready to perform any operation. The most recent action request succeeded and completed.

     

     ``UNDER_CHANGE`` - Transitive state, operations performed may or may not have valid results. Wait for an ``AVAILABLE`` status before performing operations.

     

     ``TAINTED`` - Stable state, ready to perform any operation. The stack has completed the requested operation but is not exactly what was requested. For example, a request to update to a new version failed and the stack rolled back to the current version. 

     

     ``ERROR`` - Something unexpected happened such that the provisioned product exists but the stack is not running. For example, CloudFormation received an invalid parameter value and could not launch the stack.

    

    

  StatusMessage -> (string)

    

    The current status message of the ProvisionedProduct.

    

    

  CreatedTime -> (timestamp)

    

    The UTC timestamp of the creation time.

    

    

  IdempotencyToken -> (string)

    

    A token to disambiguate duplicate requests. You can create multiple resources using the same input in multiple requests, provided that you also specify a different idempotency token for each request.

    

    

  LastRecordId -> (string)

    

    The record identifier of the last request performed on this ProvisionedProduct object.

    

    

  

