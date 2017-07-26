[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-reserved-db-instances-offerings:


****************************************
describe-reserved-db-instances-offerings
****************************************



===========
Description
===========



Lists available reserved DB instance offerings.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeReservedDBInstancesOfferings>`_


``describe-reserved-db-instances-offerings`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedDBInstancesOfferings``


========
Synopsis
========

::

    describe-reserved-db-instances-offerings
  [--reserved-db-instances-offering-id <value>]
  [--db-instance-class <value>]
  [--duration <value>]
  [--product-description <value>]
  [--offering-type <value>]
  [--multi-az | --no-multi-az]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--reserved-db-instances-offering-id`` (string)


  The offering identifier filter value. Specify this parameter to show only the available offering that matches the specified reservation identifier.

   

  Example: ``438012d3-4052-4cc7-b2e3-8d3372e0e706``  

  

``--db-instance-class`` (string)


  The DB instance class filter value. Specify this parameter to show only the available offerings matching the specified DB instance class.

  

``--duration`` (string)


  Duration filter value, specified in years or seconds. Specify this parameter to show only reservations for this duration.

   

  Valid Values: ``1 | 3 | 31536000 | 94608000``  

  

``--product-description`` (string)


  Product description filter value. Specify this parameter to show only the available offerings matching the specified product description.

  

``--offering-type`` (string)


  The offering type filter value. Specify this parameter to show only the available offerings matching the specified offering type.

   

  Valid Values: ``"Partial Upfront" | "All Upfront" | "No Upfront"``  

  

``--multi-az`` | ``--no-multi-az`` (boolean)


  The Multi-AZ filter value. Specify this parameter to show only the available offerings matching the specified Multi-AZ parameter.

  

``--filters`` (list)


  This parameter is not currently supported.

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

ReservedDBInstancesOfferings -> (list)

  

  A list of reserved DB instance offerings.

  

  (structure)

    

    This data type is used as a response element in the  describe-reserved-db-instances-offerings action. 

    

    ReservedDBInstancesOfferingId -> (string)

      

      The offering identifier.

      

      

    DBInstanceClass -> (string)

      

      The DB instance class for the reserved DB instance.

      

      

    Duration -> (integer)

      

      The duration of the offering in seconds.

      

      

    FixedPrice -> (double)

      

      The fixed price charged for this offering.

      

      

    UsagePrice -> (double)

      

      The hourly price charged for this offering.

      

      

    CurrencyCode -> (string)

      

      The currency code for the reserved DB instance offering.

      

      

    ProductDescription -> (string)

      

      The database engine used by the offering.

      

      

    OfferingType -> (string)

      

      The offering type.

      

      

    MultiAZ -> (boolean)

      

      Indicates if the offering applies to Multi-AZ deployments.

      

      

    RecurringCharges -> (list)

      

      The recurring price charged to run this reserved DB instance.

      

      (structure)

        

        This data type is used as a response element in the  describe-reserved-db-instances and  describe-reserved-db-instances-offerings actions. 

        

        RecurringChargeAmount -> (double)

          

          The amount of the recurring charge.

          

          

        RecurringChargeFrequency -> (string)

          

          The frequency of the recurring charge.

          

          

        

      

    

  

