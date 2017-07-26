[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-record:


***************
describe-record
***************



===========
Description
===========



Retrieves a paginated list of the full details of a specific request. Use this operation after calling a request operation ( provision-product ,  terminate-provisioned-product , or  update-provisioned-product ). 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeRecord>`_


========
Synopsis
========

::

    describe-record
  [--accept-language <value>]
  --id <value>
  [--page-token <value>]
  [--page-size <value>]
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


  The record identifier of the ProvisionedProduct object for which to retrieve output information. This is the ``RecordDetail.RecordId`` obtained from the request operation's response.

  

``--page-token`` (string)


  The page token of the first page retrieved. If null, this retrieves the first page of size ``page-size`` .

  

``--page-size`` (integer)


  The maximum number of items to return in the results. If more results exist than fit in the specified ``page-size`` , the value of ``NextPageToken`` in the response is non-null.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RecordDetail -> (structure)

  

  Detailed record information for the specified product. 

  

  RecordId -> (string)

    

    The identifier of the ProvisionedProduct object record.

    

    

  ProvisionedProductName -> (string)

    

    The user-friendly name of the ProvisionedProduct object.

    

    

  Status -> (string)

    

    The status of the ProvisionedProduct object.

     

     ``CREATED`` - Request created but the operation has not yet started.

     

     ``IN_PROGRESS`` - The requested operation is in-progress.

     

     ``IN_PROGRESS_IN_ERROR`` - The provisioned product is under change but the requested operation failed and some remediation is occurring. For example, a rollback.

     

     ``SUCCEEDED`` - The requested operation has successfully completed.

     

     ``FAILED`` - The requested operation has completed but has failed. Investigate using the error messages returned.

    

    

  CreatedTime -> (timestamp)

    

    The UTC timestamp of the creation time.

    

    

  UpdatedTime -> (timestamp)

    

    The time when the record for the ProvisionedProduct object was last updated.

    

    

  ProvisionedProductType -> (string)

    

    The type of the ProvisionedProduct object.

    

    

  RecordType -> (string)

    

    The record type for this record.

    

    

  ProvisionedProductId -> (string)

    

    The identifier of the ProvisionedProduct object.

    

    

  ProductId -> (string)

    

    The product identifier.

    

    

  ProvisioningArtifactId -> (string)

    

    The provisioning artifact identifier for this product. This is sometimes referred to as the product version.

    

    

  PathId -> (string)

    

    The identifier of the path for this product's provisioning.

    

    

  RecordErrors -> (list)

    

    A list of errors that occurred while processing the request.

    

    (structure)

      

      The error code and description resulting from an operation.

      

      Code -> (string)

        

        The numeric value of the error.

        

        

      Description -> (string)

        

        The text description of the error.

        

        

      

    

  RecordTags -> (list)

    

    List of tags associated with this record.

    

    (structure)

      

      A tag associated with the record, stored as a key-value pair.

      

      Key -> (string)

        

        The key for this tag.

        

        

      Value -> (string)

        

        The value for this tag.

        

        

      

    

  

RecordOutputs -> (list)

  

  A list of outputs for the specified Product object created as the result of a request. For example, a CloudFormation-backed product that creates an S3 bucket would have an output for the S3 bucket URL.

  

  (structure)

    

    An output for the specified Product object created as the result of a request. For example, a CloudFormation-backed product that creates an S3 bucket would have an output for the S3 bucket URL.

    

    OutputKey -> (string)

      

      The output key.

      

      

    OutputValue -> (string)

      

      The output value.

      

      

    Description -> (string)

      

      The text description of the output.

      

      

    

  

NextPageToken -> (string)

  

  The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

