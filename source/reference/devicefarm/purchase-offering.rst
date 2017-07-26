[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm purchase-offering:


*****************
purchase-offering
*****************



===========
Description
===========



Immediately purchases offerings for an AWS account. Offerings renew with the latest total purchased quantity for an offering, unless the renewal was overridden. The API returns a ``NotEligible`` error if the user is not permitted to invoke the operation. Please contact `aws-devicefarm-support@amazon.com <mailto:aws-devicefarm-support@amazon.com>`_ if you believe that you should be able to invoke this operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/PurchaseOffering>`_


========
Synopsis
========

::

    purchase-offering
  [--offering-id <value>]
  [--quantity <value>]
  [--offering-promotion-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--offering-id`` (string)


  The ID of the offering.

  

``--quantity`` (integer)


  The number of device slots you wish to purchase in an offering request.

  

``--offering-promotion-id`` (string)


  The ID of the offering promotion to be applied to the purchase.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

offeringTransaction -> (structure)

  

  Represents the offering transaction for the purchase result.

  

  offeringStatus -> (structure)

    

    The status of an offering transaction.

    

    type -> (string)

      

      The type specified for the offering status.

      

      

    offering -> (structure)

      

      Represents the metadata of an offering status.

      

      id -> (string)

        

        The ID that corresponds to a device offering.

        

        

      description -> (string)

        

        A string describing the offering.

        

        

      type -> (string)

        

        The type of offering (e.g., "RECURRING") for a device.

        

        

      platform -> (string)

        

        The platform of the device (e.g., ANDROID or IOS).

        

        

      recurringCharges -> (list)

        

        Specifies whether there are recurring charges for the offering.

        

        (structure)

          

          Specifies whether charges for devices will be recurring.

          

          cost -> (structure)

            

            The cost of the recurring charge.

            

            amount -> (double)

              

              The numerical amount of an offering or transaction.

              

              

            currencyCode -> (string)

              

              The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

              

              

            

          frequency -> (string)

            

            The frequency in which charges will recur.

            

            

          

        

      

    quantity -> (integer)

      

      The number of available devices in the offering.

      

      

    effectiveOn -> (timestamp)

      

      The date on which the offering is effective.

      

      

    

  transactionId -> (string)

    

    The transaction ID of the offering transaction.

    

    

  offeringPromotionId -> (string)

    

    The ID that corresponds to a device offering promotion.

    

    

  createdOn -> (timestamp)

    

    The date on which an offering transaction was created.

    

    

  cost -> (structure)

    

    The cost of an offering transaction.

    

    amount -> (double)

      

      The numerical amount of an offering or transaction.

      

      

    currencyCode -> (string)

      

      The currency code of a monetary amount. For example, ``USD`` means "U.S. dollars."

      

      

    

  

