[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-reserved-instances-listings:


************************************
describe-reserved-instances-listings
************************************



===========
Description
===========



Describes your account's Reserved Instance listings in the Reserved Instance Marketplace.

 

The Reserved Instance Marketplace matches sellers who want to resell Reserved Instance capacity that they no longer need with buyers who want to purchase additional capacity. Reserved Instances bought and sold through the Reserved Instance Marketplace work like any other Reserved Instances. 

 

As a seller, you choose to list some or all of your Reserved Instances, and you specify the upfront price to receive for them. Your Reserved Instances are then listed in the Reserved Instance Marketplace and are available for purchase. 

 

As a buyer, you specify the configuration of the Reserved Instance to purchase, and the Marketplace matches what you're searching for with what's available. The Marketplace first sells the lowest priced Reserved Instances to you, and continues to sell available Reserved Instance listings to you until your demand is met. You are charged based on the total price of all of the listings that you purchase.

 

For more information, see `Reserved Instance Marketplace`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    describe-reserved-instances-listings
  [--reserved-instances-id <value>]
  [--reserved-instances-listing-id <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-instances-id`` (string)


  One or more Reserved Instance IDs.

  

``--reserved-instances-listing-id`` (string)


  One or more Reserved Instance listing IDs.

  

``--filters`` (list)


  One or more filters.

   

   
  * ``reserved-instances-id`` - The ID of the Reserved Instances. 
   
  * ``reserved-instances-listing-id`` - The ID of the Reserved Instances listing. 
   
  * ``status`` - The status of the Reserved Instance listing (``pending`` | ``active`` | ``cancelled`` | ``closed`` ). 
   
  * ``status-message`` - The reason for the status. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ReservedInstancesListings -> (list)

  

  Information about the Reserved Instance listing.

  

  (structure)

    

    Describes a Reserved Instance listing.

    

    ReservedInstancesListingId -> (string)

      

      The ID of the Reserved Instance listing.

      

      

    ReservedInstancesId -> (string)

      

      The ID of the Reserved Instance.

      

      

    CreateDate -> (timestamp)

      

      The time the listing was created.

      

      

    UpdateDate -> (timestamp)

      

      The last modified timestamp of the listing.

      

      

    Status -> (string)

      

      The status of the Reserved Instance listing.

      

      

    StatusMessage -> (string)

      

      The reason for the current status of the Reserved Instance listing. The response can be blank.

      

      

    InstanceCounts -> (list)

      

      The number of instances in this state.

      

      (structure)

        

        Describes a Reserved Instance listing state.

        

        State -> (string)

          

          The states of the listed Reserved Instances.

          

          

        InstanceCount -> (integer)

          

          The number of listed Reserved Instances in the state specified by the ``state`` .

          

          

        

      

    PriceSchedules -> (list)

      

      The price of the Reserved Instance listing.

      

      (structure)

        

        Describes the price for a Reserved Instance.

        

        Term -> (long)

          

          The number of months remaining in the reservation. For example, 2 is the second to the last month before the capacity reservation expires.

          

          

        Price -> (double)

          

          The fixed price for the term.

          

          

        CurrencyCode -> (string)

          

          The currency for transacting the Reserved Instance resale. At this time, the only supported currency is ``USD`` .

          

          

        Active -> (boolean)

          

          The current price schedule, as determined by the term remaining for the Reserved Instance in the listing.

           

          A specific price schedule is always in effect, but only one price schedule can be active at any time. Take, for example, a Reserved Instance listing that has five months remaining in its term. When you specify price schedules for five months and two months, this means that schedule 1, covering the first three months of the remaining term, will be active during months 5, 4, and 3. Then schedule 2, covering the last two months of the term, will be active for months 2 and 1.

          

          

        

      

    Tags -> (list)

      

      Any tags assigned to the resource.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag. 

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    ClientToken -> (string)

      

      A unique, case-sensitive key supplied by the client to ensure that the request is idempotent. For more information, see `Ensuring Idempotency`_ .

      

      

    

  



.. _Ensuring Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html
.. _Reserved Instance Marketplace: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-general.html
