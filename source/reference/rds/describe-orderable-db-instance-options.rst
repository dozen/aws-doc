[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-orderable-db-instance-options:


**************************************
describe-orderable-db-instance-options
**************************************



===========
Description
===========



Returns a list of orderable DB instance options for the specified engine. 



``describe-orderable-db-instance-options`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``OrderableDBInstanceOptions``


========
Synopsis
========

::

    describe-orderable-db-instance-options
  --engine <value>
  [--engine-version <value>]
  [--db-instance-class <value>]
  [--license-model <value>]
  [--vpc | --no-vpc]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--engine`` (string)


  The name of the engine to retrieve DB instance options for. 

  

``--engine-version`` (string)


  The engine version filter value. Specify this parameter to show only the available offerings matching the specified engine version. 

  

``--db-instance-class`` (string)


  The DB instance class filter value. Specify this parameter to show only the available offerings matching the specified DB instance class. 

  

``--license-model`` (string)


  The license model filter value. Specify this parameter to show only the available offerings matching the specified license model. 

  

``--vpc`` | ``--no-vpc`` (boolean)


  The VPC filter value. Specify this parameter to show only the available VPC or non-VPC offerings. 

  

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

OrderableDBInstanceOptions -> (list)

  

  An  OrderableDBInstanceOption structure containing information about orderable options for the DB instance.

  

  (structure)

    

    Contains a list of available options for a DB instance 

     

    This data type is used as a response element in the  describe-orderable-db-instance-options action. 

    

    Engine -> (string)

      

      The engine type of the orderable DB instance. 

      

      

    EngineVersion -> (string)

      

      The engine version of the orderable DB instance. 

      

      

    DBInstanceClass -> (string)

      

      The DB instance class for the orderable DB instance. 

      

      

    LicenseModel -> (string)

      

      The license model for the orderable DB instance. 

      

      

    AvailabilityZones -> (list)

      

      A list of Availability Zones for the orderable DB instance. 

      

      (structure)

        

        Contains Availability Zone information. 

         

        This data type is used as an element in the following data type: 

        
        *  OrderableDBInstanceOption 
        

        

        

        Name -> (string)

          

          The name of the availability zone. 

          

          

        

      

    MultiAZCapable -> (boolean)

      

      Indicates whether this orderable DB instance is multi-AZ capable. 

      

      

    ReadReplicaCapable -> (boolean)

      

      Indicates whether this orderable DB instance can have a Read Replica. 

      

      

    Vpc -> (boolean)

      

      Indicates whether this is a VPC orderable DB instance. 

      

      

    SupportsStorageEncryption -> (boolean)

      

      Indicates whether this orderable DB instance supports encrypted storage. 

      

      

    StorageType -> (string)

      

      Indicates the storage type for this orderable DB instance. 

      

      

    SupportsIops -> (boolean)

      

      Indicates whether this orderable DB instance supports provisioned IOPS. 

      

      

    SupportsEnhancedMonitoring -> (boolean)

      

      Indicates whether the DB instance supports enhanced monitoring at intervals from 1 to 60 seconds.

      

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous OrderableDBInstanceOptions request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

