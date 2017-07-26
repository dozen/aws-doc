[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 get-reserved-instances-exchange-quote:


*************************************
get-reserved-instances-exchange-quote
*************************************



===========
Description
===========



Returns details about the values and term of your specified Convertible Reserved Instances. When a target configuration is specified, it returns information about whether the exchange is valid and can be performed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/GetReservedInstancesExchangeQuote>`_


========
Synopsis
========

::

    get-reserved-instances-exchange-quote
  [--dry-run | --no-dry-run]
  --reserved-instance-ids <value>
  [--target-configurations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--reserved-instance-ids`` (list)


  The IDs of the Convertible Reserved Instances to exchange.

  



Syntax::

  "string" "string" ...



``--target-configurations`` (list)


  The configuration requirements of the Convertible Reserved Instances to exchange for your current Convertible Reserved Instances.

  



Shorthand Syntax::

    InstanceCount=integer,OfferingId=string ...




JSON Syntax::

  [
    {
      "InstanceCount": integer,
      "OfferingId": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CurrencyCode -> (string)

  

  The currency of the transaction.

  

  

IsValidExchange -> (boolean)

  

  If ``true`` , the exchange is valid. If ``false`` , the exchange cannot be completed.

  

  

OutputReservedInstancesWillExpireAt -> (timestamp)

  

  The new end date of the reservation term.

  

  

PaymentDue -> (string)

  

  The total true upfront charge for the exchange.

  

  

ReservedInstanceValueRollup -> (structure)

  

  The cost associated with the Reserved Instance.

  

  HourlyPrice -> (string)

    

    The hourly rate of the reservation.

    

    

  RemainingTotalValue -> (string)

    

    The balance of the total value (the sum of remainingUpfrontValue + hourlyPrice * number of hours remaining).

    

    

  RemainingUpfrontValue -> (string)

    

    The remaining upfront cost of the reservation.

    

    

  

ReservedInstanceValueSet -> (list)

  

  The configuration of your Convertible Reserved Instances.

  

  (structure)

    

    The total value of the Convertible Reserved Instance.

    

    ReservationValue -> (structure)

      

      The total value of the Convertible Reserved Instance that you are exchanging.

      

      HourlyPrice -> (string)

        

        The hourly rate of the reservation.

        

        

      RemainingTotalValue -> (string)

        

        The balance of the total value (the sum of remainingUpfrontValue + hourlyPrice * number of hours remaining).

        

        

      RemainingUpfrontValue -> (string)

        

        The remaining upfront cost of the reservation.

        

        

      

    ReservedInstanceId -> (string)

      

      The ID of the Convertible Reserved Instance that you are exchanging.

      

      

    

  

TargetConfigurationValueRollup -> (structure)

  

  The cost associated with the Reserved Instance.

  

  HourlyPrice -> (string)

    

    The hourly rate of the reservation.

    

    

  RemainingTotalValue -> (string)

    

    The balance of the total value (the sum of remainingUpfrontValue + hourlyPrice * number of hours remaining).

    

    

  RemainingUpfrontValue -> (string)

    

    The remaining upfront cost of the reservation.

    

    

  

TargetConfigurationValueSet -> (list)

  

  The values of the target Convertible Reserved Instances.

  

  (structure)

    

    The total value of the new Convertible Reserved Instances.

    

    ReservationValue -> (structure)

      

      The total value of the Convertible Reserved Instances that make up the exchange. This is the sum of the list value, remaining upfront price, and additional upfront cost of the exchange.

      

      HourlyPrice -> (string)

        

        The hourly rate of the reservation.

        

        

      RemainingTotalValue -> (string)

        

        The balance of the total value (the sum of remainingUpfrontValue + hourlyPrice * number of hours remaining).

        

        

      RemainingUpfrontValue -> (string)

        

        The remaining upfront cost of the reservation.

        

        

      

    TargetConfiguration -> (structure)

      

      The configuration of the Convertible Reserved Instances that make up the exchange.

      

      InstanceCount -> (integer)

        

        The number of instances the Convertible Reserved Instance offering can be applied to. This parameter is reserved and cannot be specified in a request

        

        

      OfferingId -> (string)

        

        The ID of the Convertible Reserved Instance offering.

        

        

      

    

  

ValidationFailureReason -> (string)

  

  Describes the reason why the exchange cannot be completed.

  

  

