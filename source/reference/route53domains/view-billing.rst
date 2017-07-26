[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains view-billing:


************
view-billing
************



===========
Description
===========



Returns all the domain-related billing records for the current AWS account for a specified period



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/ViewBilling>`_


========
Synopsis
========

::

    view-billing
  [--marker <value>]
  [--max-items <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--marker`` (string)


  For an initial request for a list of billing records, omit this element. If the number of billing records that are associated with the current AWS account during the specified period is greater than the value that you specified for ``MaxItems`` , you can use ``Marker`` to return additional billing records. Get the value of ``NextPageMarker`` from the previous response, and submit another request that includes the value of ``NextPageMarker`` in the ``Marker`` element. 

   

  Constraints: The marker must match the value of ``NextPageMarker`` that was returned in the previous response.

  

``--max-items`` (integer)


  The number of billing records to be returned.

   

  Default: 20

  

``--start-time`` (timestamp)


  The beginning date and time for the time period for which you want a list of billing records. Specify the date in Unix time format.

  

``--end-time`` (timestamp)


  The end date and time for the time period for which you want a list of billing records. Specify the date in Unix time format.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextPageMarker -> (string)

  

  If there are more billing records than you specified for ``MaxItems`` in the request, submit another request and include the value of ``NextPageMarker`` in the value of ``Marker`` .

  

  

BillingRecords -> (list)

  

  A summary of billing records.

  

  (structure)

    

    Information for one billing record.

    

    DomainName -> (string)

      

      The name of the domain that the billing record applies to. If the domain name contains characters other than a-z, 0-9, and - (hyphen), such as an internationalized domain name, then this value is in Punycode. For more information, see `DNS Domain Name Format <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DomainNameFormat.html>`_ in the *Amazon Route 53 Developer Guidezzz* .

      

      

    Operation -> (string)

      

      The operation that you were charged for.

      

      

    InvoiceId -> (string)

      

      The ID of the invoice that is associated with the billing record.

      

      

    BillDate -> (timestamp)

      

      The date that the operation was billed, in Unix format.

      

      

    Price -> (double)

      

      The price that you were charged for the operation, in US dollars.

       

      Example value: 12.0

      

      

    

  

