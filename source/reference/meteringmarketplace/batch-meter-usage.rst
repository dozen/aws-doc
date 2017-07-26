[ :ref:`aws <cli:aws>` . :ref:`meteringmarketplace <cli:aws meteringmarketplace>` ]

.. _cli:aws meteringmarketplace batch-meter-usage:


*****************
batch-meter-usage
*****************



===========
Description
===========



batch-meter-usage is called from a SaaS application listed on the AWS Marketplace to post metering records for a set of customers.

 

For identical requests, the API is idempotent; requests can be retried with the same records or a subset of the input records.

 

Every request to batch-meter-usage is for one product. If you need to meter usage for multiple products, you must make multiple calls to BatchMeterUsage.

 

batch-meter-usage can process up to 25 UsageRecords at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/meteringmarketplace-2016-01-14/BatchMeterUsage>`_


========
Synopsis
========

::

    batch-meter-usage
  --usage-records <value>
  --product-code <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--usage-records`` (list)


  The set of UsageRecords to submit. batch-meter-usage accepts up to 25 UsageRecords at a time.

  



Shorthand Syntax::

    Timestamp=timestamp,CustomerIdentifier=string,Dimension=string,Quantity=integer ...




JSON Syntax::

  [
    {
      "Timestamp": timestamp,
      "CustomerIdentifier": "string",
      "Dimension": "string",
      "Quantity": integer
    }
    ...
  ]



``--product-code`` (string)


  Product code is used to uniquely identify a product in AWS Marketplace. The product code should be the same as the one used during the publishing of a new product.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Results -> (list)

  

  Contains all UsageRecords processed by BatchMeterUsage. These records were either honored by AWS Marketplace Metering Service or were invalid.

  

  (structure)

    

    A UsageRecordResult indicates the status of a given UsageRecord processed by BatchMeterUsage.

    

    UsageRecord -> (structure)

      

      The UsageRecord that was part of the batch-meter-usage request.

      

      Timestamp -> (timestamp)

        

        Timestamp of the hour, recorded in UTC. The seconds and milliseconds portions of the timestamp will be ignored.

         

        Your application can meter usage for up to one hour in the past.

        

        

      CustomerIdentifier -> (string)

        

        The CustomerIdentifier is obtained through the resolve-customer operation and represents an individual buyer in your application.

        

        

      Dimension -> (string)

        

        During the process of registering a product on AWS Marketplace, up to eight dimensions are specified. These represent different units of value in your application.

        

        

      Quantity -> (integer)

        

        The quantity of usage consumed by the customer for the given dimension and time.

        

        

      

    MeteringRecordId -> (string)

      

      The MeteringRecordId is a unique identifier for this metering event.

      

      

    Status -> (string)

      

      The UsageRecordResult Status indicates the status of an individual UsageRecord processed by BatchMeterUsage.

       

       
      * *Success* - The UsageRecord was accepted and honored by BatchMeterUsage. 
       
      * *CustomerNotSubscribed* - The CustomerIdentifier specified is not subscribed to your product. The UsageRecord was not honored. Future UsageRecords for this customer will fail until the customer subscribes to your product. 
       
      * *DuplicateRecord* - Indicates that the UsageRecord was invalid and not honored. A previously metered UsageRecord had the same customer, dimension, and time, but a different quantity. 
       

      

      

    

  

UnprocessedRecords -> (list)

  

  Contains all UsageRecords that were not processed by BatchMeterUsage. This is a list of UsageRecords. You can retry the failed request by making another batch-meter-usage call with this list as input in the BatchMeterUsageRequest.

  

  (structure)

    

    A UsageRecord indicates a quantity of usage for a given product, customer, dimension and time.

     

    Multiple requests with the same UsageRecords as input will be deduplicated to prevent double charges.

    

    Timestamp -> (timestamp)

      

      Timestamp of the hour, recorded in UTC. The seconds and milliseconds portions of the timestamp will be ignored.

       

      Your application can meter usage for up to one hour in the past.

      

      

    CustomerIdentifier -> (string)

      

      The CustomerIdentifier is obtained through the resolve-customer operation and represents an individual buyer in your application.

      

      

    Dimension -> (string)

      

      During the process of registering a product on AWS Marketplace, up to eight dimensions are specified. These represent different units of value in your application.

      

      

    Quantity -> (integer)

      

      The quantity of usage consumed by the customer for the given dimension and time.

      

      

    

  

