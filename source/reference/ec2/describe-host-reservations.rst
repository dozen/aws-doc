[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-host-reservations:


**************************
describe-host-reservations
**************************



===========
Description
===========



Describes Dedicated Host Reservations which are associated with Dedicated Hosts in your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeHostReservations>`_


========
Synopsis
========

::

    describe-host-reservations
  [--filter <value>]
  [--host-reservation-id-set <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (list)


  One or more filters.

   

   
  * ``instance-family`` - The instance family (e.g., ``m4`` ). 
   
  * ``payment-option`` - The payment option (``NoUpfront`` | ``PartialUpfront`` | ``AllUpfront`` ). 
   
  * ``state`` - The state of the reservation (``payment-pending`` | ``payment-failed`` | ``active`` | ``retired`` ). 
   

  



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



``--host-reservation-id-set`` (list)


  One or more host reservation IDs.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results can be seen by sending another request with the returned ``nextToken`` value. This value can be between 5 and 500; if ``maxResults`` is given a larger value than 500, you will receive an error.

  

``--next-token`` (string)


  The token to use to retrieve the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HostReservationSet -> (list)

  

  Details about the reservation's configuration.

  

  (structure)

    

    Details about the Dedicated Host Reservation and associated Dedicated Hosts.

    

    Count -> (integer)

      

      The number of Dedicated Hosts the reservation is associated with.

      

      

    CurrencyCode -> (string)

      

      The currency in which the ``upfrontPrice`` and ``hourlyPrice`` amounts are specified. At this time, the only supported currency is ``USD`` .

      

      

    Duration -> (integer)

      

      The length of the reservation's term, specified in seconds. Can be ``31536000 (1 year)`` | ``94608000 (3 years)`` .

      

      

    End -> (timestamp)

      

      The date and time that the reservation ends.

      

      

    HostIdSet -> (list)

      

      The IDs of the Dedicated Hosts associated with the reservation.

      

      (string)

        

        

      

    HostReservationId -> (string)

      

      The ID of the reservation that specifies the associated Dedicated Hosts.

      

      

    HourlyPrice -> (string)

      

      The hourly price of the reservation.

      

      

    InstanceFamily -> (string)

      

      The instance family of the Dedicated Host Reservation. The instance family on the Dedicated Host must be the same in order for it to benefit from the reservation.

      

      

    OfferingId -> (string)

      

      The ID of the reservation. This remains the same regardless of which Dedicated Hosts are associated with it.

      

      

    PaymentOption -> (string)

      

      The payment option selected for this reservation.

      

      

    Start -> (timestamp)

      

      The date and time that the reservation started.

      

      

    State -> (string)

      

      The state of the reservation.

      

      

    UpfrontPrice -> (string)

      

      The upfront price of the reservation.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

