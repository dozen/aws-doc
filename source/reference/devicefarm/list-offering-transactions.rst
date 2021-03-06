[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-offering-transactions:


**************************
list-offering-transactions
**************************



===========
Description
===========



Returns a list of all historical purchases, renewals, and system renewal transactions for an AWS account. The list is paginated and ordered by a descending timestamp (most recent transactions are first). The API returns a ``NotEligible`` error if the user is not permitted to invoke the operation. Please contact `aws-devicefarm-support@amazon.com <mailto:aws-devicefarm-support@amazon.com>`_ if you believe that you should be able to invoke this operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/ListOfferingTransactions>`_


``list-offering-transactions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``offeringTransactions``


========
Synopsis
========

::

    list-offering-transactions
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

offeringTransactions -> (list)

  

  The audit log of subscriptions you have purchased and modified through AWS Device Farm.

  

  (structure)

    

    Represents the metadata of an offering transaction.

    

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

        

        

      

    

  

nextToken -> (string)

  

  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

  

