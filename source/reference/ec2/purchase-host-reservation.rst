[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 purchase-host-reservation:


*************************
purchase-host-reservation
*************************



===========
Description
===========



Purchase a reservation with configurations that match those of your Dedicated Host. You must have active Dedicated Hosts in your account before you purchase a reservation. This action results in the specified reservation being purchased and charged to your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/PurchaseHostReservation>`_


========
Synopsis
========

::

    purchase-host-reservation
  [--client-token <value>]
  [--currency-code <value>]
  --host-id-set <value>
  [--limit-price <value>]
  --offering-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--currency-code`` (string)


  The currency in which the ``totalUpfrontPrice`` , ``LimitPrice`` , and ``totalHourlyPrice`` amounts are specified. At this time, the only supported currency is ``USD`` .

  

  Possible values:

  
  *   ``USD``

  

  

``--host-id-set`` (list)


  The ID/s of the Dedicated Host/s that the reservation will be associated with.

  



Syntax::

  "string" "string" ...



``--limit-price`` (string)


  The specified limit is checked against the total upfront cost of the reservation (calculated as the offering's upfront cost multiplied by the host count). If the total upfront cost is greater than the specified price limit, the request will fail. This is used to ensure that the purchase does not exceed the expected upfront cost of the purchase. At this time, the only supported currency is ``USD`` . For example, to indicate a limit price of USD 100, specify 100.00.

  

``--offering-id`` (string)


  The ID of the offering.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ClientToken -> (string)

  

  Unique, case-sensitive identifier you provide to ensure idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ in the *Amazon Elastic Compute Cloud User Guide*  

  

  

CurrencyCode -> (string)

  

  The currency in which the ``totalUpfrontPrice`` and ``totalHourlyPrice`` amounts are specified. At this time, the only supported currency is ``USD`` .

  

  

Purchase -> (list)

  

  Describes the details of the purchase.

  

  (structure)

    

    Describes the result of the purchase.

    

    CurrencyCode -> (string)

      

      The currency in which the ``UpfrontPrice`` and ``HourlyPrice`` amounts are specified. At this time, the only supported currency is ``USD`` .

      

      

    Duration -> (integer)

      

      The duration of the reservation's term in seconds.

      

      

    HostIdSet -> (list)

      

      The IDs of the Dedicated Hosts associated with the reservation.

      

      (string)

        

        

      

    HostReservationId -> (string)

      

      The ID of the reservation.

      

      

    HourlyPrice -> (string)

      

      The hourly price of the reservation per hour.

      

      

    InstanceFamily -> (string)

      

      The instance family on the Dedicated Host that the reservation can be associated with.

      

      

    PaymentOption -> (string)

      

      The payment option for the reservation.

      

      

    UpfrontPrice -> (string)

      

      The upfront price of the reservation.

      

      

    

  

TotalHourlyPrice -> (string)

  

  The total hourly price of the reservation calculated per hour.

  

  

TotalUpfrontPrice -> (string)

  

  The total amount that will be charged to your account when you purchase the reservation.

  

  

