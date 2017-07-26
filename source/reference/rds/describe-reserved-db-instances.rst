[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-reserved-db-instances:


******************************
describe-reserved-db-instances
******************************



===========
Description
===========



Returns information about reserved DB instances for this account, or about a specified reserved DB instance. 



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
  [--generate-cli-skeleton]




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

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

          

          

        

      

    

  

