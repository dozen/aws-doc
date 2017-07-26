[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds purchase-reserved-db-instances-offering:


***************************************
purchase-reserved-db-instances-offering
***************************************



===========
Description
===========



Purchases a reserved DB instance offering. 



========
Synopsis
========

::

    purchase-reserved-db-instances-offering
  --reserved-db-instances-offering-id <value>
  [--reserved-db-instance-id <value>]
  [--db-instance-count <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-db-instances-offering-id`` (string)


  The ID of the Reserved DB instance offering to purchase. 

   

  Example: 438012d3-4052-4cc7-b2e3-8d3372e0e706

  

``--reserved-db-instance-id`` (string)


  Customer-specified identifier to track this reservation. 

   

  Example: myreservationID

  

``--db-instance-count`` (integer)


  The number of instances to reserve. 

   

  Default: ``1`` 

  

``--tags`` (list)


  A list of tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ReservedDBInstance -> (structure)

  

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

        

        

      

    

  

