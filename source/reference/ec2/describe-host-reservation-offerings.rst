[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-host-reservation-offerings:


***********************************
describe-host-reservation-offerings
***********************************



===========
Description
===========



Describes the Dedicated Host Reservations that are available to purchase.

 

The results describe all the Dedicated Host Reservation offerings, including offerings that may not match the instance family and region of your Dedicated Hosts. When purchasing an offering, ensure that the the instance family and region of the offering matches that of the Dedicated Host/s it will be associated with. For an overview of supported instance types, see `Dedicated Hosts Overview <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-hosts-overview.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeHostReservationOfferings>`_


========
Synopsis
========

::

    describe-host-reservation-offerings
  [--filter <value>]
  [--max-duration <value>]
  [--max-results <value>]
  [--min-duration <value>]
  [--next-token <value>]
  [--offering-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (list)


  One or more filters.

   

   
  * ``instance-family`` - The instance family of the offering (e.g., ``m4`` ). 
   
  * ``payment-option`` - The payment option (``NoUpfront`` | ``PartialUpfront`` | ``AllUpfront`` ). 
   

  



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



``--max-duration`` (integer)


  This is the maximum duration of the reservation you'd like to purchase, specified in seconds. Reservations are available in one-year and three-year terms. The number of seconds specified must be the number of seconds in a year (365x24x60x60) times one of the supported durations (1 or 3). For example, specify 94608000 for three years.

  

``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results can be seen by sending another request with the returned ``nextToken`` value. This value can be between 5 and 500; if ``maxResults`` is given a larger value than 500, you will receive an error.

  

``--min-duration`` (integer)


  This is the minimum duration of the reservation you'd like to purchase, specified in seconds. Reservations are available in one-year and three-year terms. The number of seconds specified must be the number of seconds in a year (365x24x60x60) times one of the supported durations (1 or 3). For example, specify 31536000 for one year.

  

``--next-token`` (string)


  The token to use to retrieve the next page of results.

  

``--offering-id`` (string)


  The ID of the reservation offering.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

OfferingSet -> (list)

  

  Information about the offerings.

  

  (structure)

    

    Details about the Dedicated Host Reservation offering.

    

    CurrencyCode -> (string)

      

      The currency of the offering.

      

      

    Duration -> (integer)

      

      The duration of the offering (in seconds).

      

      

    HourlyPrice -> (string)

      

      The hourly price of the offering.

      

      

    InstanceFamily -> (string)

      

      The instance family of the offering.

      

      

    OfferingId -> (string)

      

      The ID of the offering.

      

      

    PaymentOption -> (string)

      

      The available payment option.

      

      

    UpfrontPrice -> (string)

      

      The upfront price of the offering. Does not apply to No Upfront offerings.

      

      

    

  

