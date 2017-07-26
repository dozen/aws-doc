[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-reserved-instances-listing:


*********************************
create-reserved-instances-listing
*********************************



===========
Description
===========



Creates a listing for Amazon EC2 Reserved Instances to be sold in the Reserved Instance Marketplace. You can submit one Reserved Instance listing at a time. To get a list of your Reserved Instances, you can use the  describe-reserved-instances operation.

 

The Reserved Instance Marketplace matches sellers who want to resell Reserved Instance capacity that they no longer need with buyers who want to purchase additional capacity. Reserved Instances bought and sold through the Reserved Instance Marketplace work like any other Reserved Instances.

 

To sell your Reserved Instances, you must first register as a seller in the Reserved Instance Marketplace. After completing the registration process, you can create a Reserved Instance Marketplace listing of some or all of your Reserved Instances, and specify the upfront price to receive for them. Your Reserved Instance listings then become available for purchase. To view the details of your Reserved Instance listing, you can use the  describe-reserved-instances-listings operation.

 

For more information, see `Reserved Instance Marketplace`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    create-reserved-instances-listing
  --reserved-instances-id <value>
  --instance-count <value>
  --price-schedules <value>
  --client-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-instances-id`` (string)


  The ID of the active Reserved Instance.

  

``--instance-count`` (integer)


  The number of instances that are a part of a Reserved Instance account to be listed in the Reserved Instance Marketplace. This number should be less than or equal to the instance count associated with the Reserved Instance ID specified in this call.

  

``--price-schedules`` (list)


  A list specifying the price of the Reserved Instance for each month remaining in the Reserved Instance term.

  



Shorthand Syntax::

    Term=long,Price=double,CurrencyCode=string ...




JSON Syntax::

  [
    {
      "Term": long,
      "Price": double,
      "CurrencyCode": "USD"
    }
    ...
  ]



``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure idempotency of your listings. This helps avoid duplicate listings. For more information, see `Ensuring Idempotency`_ .

  

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
