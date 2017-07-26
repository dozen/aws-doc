[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 get-host-reservation-purchase-preview:


*************************************
get-host-reservation-purchase-preview
*************************************



===========
Description
===========



Preview a reservation purchase with configurations that match those of your Dedicated Host. You must have active Dedicated Hosts in your account before you purchase a reservation.

 

This is a preview of the  purchase-host-reservation action and does not result in the offering being purchased.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/GetHostReservationPurchasePreview>`_


========
Synopsis
========

::

    get-host-reservation-purchase-preview
  --host-id-set <value>
  --offering-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--host-id-set`` (list)


  The ID/s of the Dedicated Host/s that the reservation will be associated with.

  



Syntax::

  "string" "string" ...



``--offering-id`` (string)


  The offering ID of the reservation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CurrencyCode -> (string)

  

  The currency in which the ``totalUpfrontPrice`` and ``totalHourlyPrice`` amounts are specified. At this time, the only supported currency is ``USD`` .

  

  

Purchase -> (list)

  

  The purchase information of the Dedicated Host Reservation and the Dedicated Hosts associated with it.

  

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

  

  The potential total hourly price of the reservation per hour.

  

  

TotalUpfrontPrice -> (string)

  

  The potential total upfront price. This is billed immediately.

  

  

