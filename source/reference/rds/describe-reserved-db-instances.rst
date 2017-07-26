[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-reserved-db-instances:


******************************
describe-reserved-db-instances
******************************



===========
Description
===========



Returns information about reserved DB instances for this account, or about a specified reserved DB instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeReservedDBInstances>`_


``describe-reserved-db-instances`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedDBInstances``


========
Synopsis
========

::

    describe-reserved-db-instances
  [--reserved-db-instance-id <value>]
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

``--reserved-db-instance-id`` (string)


  The reserved DB instance identifier filter value. Specify this parameter to show only the reservation that matches the specified reservation ID.

  

``--reserved-db-instances-offering-id`` (string)


  The offering identifier filter value. Specify this parameter to show only purchased reservations matching the specified offering identifier.

  

``--db-instance-class`` (string)


  The DB instance class filter value. Specify this parameter to show only those reservations matching the specified DB instances class.

  

``--duration`` (string)


  The duration filter value, specified in years or seconds. Specify this parameter to show only reservations for this duration.

   

  Valid Values: ``1 | 3 | 31536000 | 94608000``  

  

``--product-description`` (string)


  The product description filter value. Specify this parameter to show only those reservations matching the specified product description.

  

``--offering-type`` (string)


  The offering type filter value. Specify this parameter to show only the available offerings matching the specified offering type.

   

  Valid Values: ``"Partial Upfront" | "All Upfront" | "No Upfront"``  

  

``--multi-az`` | ``--no-multi-az`` (boolean)


  The Multi-AZ filter value. Specify this parameter to show only those reservations matching the specified Multi-AZ parameter.

  

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

  

  

ReservedDBInstances -> (list)

  

  A list of reserved DB instances.

  

  (structure)

    

    This data type is used as a response element in the  describe-reserved-db-instances and  purchase-reserved-db-instances-offering actions. 

    

    ReservedDBInstanceId -> (string)

      

      The unique identifier for the reservation.

      

      

    ReservedDBInstancesOfferingId -> (string)

      

      The offering identifier.

      

      

    DBInstanceClass -> (string)

      

      The DB instance class for the reserved DB instance.

      

      

    StartTime -> (timestamp)

      

      The time the reservation started.

      

      

    Duration -> (integer)

      

      The duration of the reservation in seconds.

      

      

    FixedPrice -> (double)

      

      The fixed price charged for this reserved DB instance.

      

      

    UsagePrice -> (double)

      

      The hourly price charged for this reserved DB instance.

      

      

    CurrencyCode -> (string)

      

      The currency code for the reserved DB instance.

      

      

    DBInstanceCount -> (integer)

      

      The number of reserved DB instances.

      

      

    ProductDescription -> (string)

      

      The description of the reserved DB instance.

      

      

    OfferingType -> (string)

      

      The offering type of this reserved DB instance.

      

      

    MultiAZ -> (boolean)

      

      Indicates if the reservation applies to Multi-AZ deployments.

      

      

    State -> (string)

      

      The state of the reserved DB instance.

      

      

    RecurringCharges -> (list)

      

      The recurring price charged to run this reserved DB instance.

      

      (structure)

        

        This data type is used as a response element in the  describe-reserved-db-instances and  describe-reserved-db-instances-offerings actions. 

        

        RecurringChargeAmount -> (double)

          

          The amount of the recurring charge.

          

          

        RecurringChargeFrequency -> (string)

          

          The frequency of the recurring charge.

          

          

        

      

    ReservedDBInstanceArn -> (string)

      

      The Amazon Resource Name (ARN) for the reserved DB instance.

      

      

    

  

