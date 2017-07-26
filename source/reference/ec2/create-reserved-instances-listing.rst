[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-reserved-instances-listing:


*********************************
create-reserved-instances-listing
*********************************



===========
Description
===========



Creates a listing for Amazon EC2 Standard Reserved Instances to be sold in the Reserved Instance Marketplace. You can submit one Standard Reserved Instance listing at a time. To get a list of your Standard Reserved Instances, you can use the  describe-reserved-instances operation.

 

.. note::

   

  Only Standard Reserved Instances with a capacity reservation can be sold in the Reserved Instance Marketplace. Convertible Reserved Instances and Standard Reserved Instances with a regional benefit cannot be sold.

   

 

The Reserved Instance Marketplace matches sellers who want to resell Standard Reserved Instance capacity that they no longer need with buyers who want to purchase additional capacity. Reserved Instances bought and sold through the Reserved Instance Marketplace work like any other Reserved Instances.

 

To sell your Standard Reserved Instances, you must first register as a seller in the Reserved Instance Marketplace. After completing the registration process, you can create a Reserved Instance Marketplace listing of some or all of your Standard Reserved Instances, and specify the upfront price to receive for them. Your Standard Reserved Instance listings then become available for purchase. To view the details of your Standard Reserved Instance listing, you can use the  describe-reserved-instances-listings operation.

 

For more information, see `Reserved Instance Marketplace <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-general.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateReservedInstancesListing>`_


========
Synopsis
========

::

    create-reserved-instances-listing
  --client-token <value>
  --instance-count <value>
  --price-schedules <value>
  --reserved-instances-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure idempotency of your listings. This helps avoid duplicate listings. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

  

``--instance-count`` (integer)


  The number of instances that are a part of a Reserved Instance account to be listed in the Reserved Instance Marketplace. This number should be less than or equal to the instance count associated with the Reserved Instance ID specified in this call.

  

``--price-schedules`` (list)


  A list specifying the price of the Standard Reserved Instance for each month remaining in the Reserved Instance term.

  



Shorthand Syntax::

    CurrencyCode=string,Price=double,Term=long ...




JSON Syntax::

  [
    {
      "CurrencyCode": "USD",
      "Price": double,
      "Term": long
    }
    ...
  ]



``--reserved-instances-id`` (string)


  The ID of the active Standard Reserved Instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ReservedInstancesListings -> (list)

  

  Information about the Standard Reserved Instance listing.

  

  (structure)

    

    Describes a Reserved Instance listing.

    

    ClientToken -> (string)

      

      A unique, case-sensitive key supplied by the client to ensure that the request is idempotent. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

      

      

    CreateDate -> (timestamp)

      

      The time the listing was created.

      

      

    InstanceCounts -> (list)

      

      The number of instances in this state.

      

      (structure)

        

        Describes a Reserved Instance listing state.

        

        InstanceCount -> (integer)

          

          The number of listed Reserved Instances in the state specified by the ``state`` .

          

          

        State -> (string)

          

          The states of the listed Reserved Instances.

          

          

        

      

    PriceSchedules -> (list)

      

      The price of the Reserved Instance listing.

      

      (structure)

        

        Describes the price for a Reserved Instance.

        

        Active -> (boolean)

          

          The current price schedule, as determined by the term remaining for the Reserved Instance in the listing.

           

          A specific price schedule is always in effect, but only one price schedule can be active at any time. Take, for example, a Reserved Instance listing that has five months remaining in its term. When you specify price schedules for five months and two months, this means that schedule 1, covering the first three months of the remaining term, will be active during months 5, 4, and 3. Then schedule 2, covering the last two months of the term, will be active for months 2 and 1.

          

          

        CurrencyCode -> (string)

          

          The currency for transacting the Reserved Instance resale. At this time, the only supported currency is ``USD`` .

          

          

        Price -> (double)

          

          The fixed price for the term.

          

          

        Term -> (long)

          

          The number of months remaining in the reservation. For example, 2 is the second to the last month before the capacity reservation expires.

          

          

        

      

    ReservedInstancesId -> (string)

      

      The ID of the Reserved Instance.

      

      

    ReservedInstancesListingId -> (string)

      

      The ID of the Reserved Instance listing.

      

      

    Status -> (string)

      

      The status of the Reserved Instance listing.

      

      

    StatusMessage -> (string)

      

      The reason for the current status of the Reserved Instance listing. The response can be blank.

      

      

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

          

          

        

      

    UpdateDate -> (timestamp)

      

      The last modified timestamp of the listing.

      

      

    

  

