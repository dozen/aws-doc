[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-orderable-replication-instances:


****************************************
describe-orderable-replication-instances
****************************************



===========
Description
===========



Returns information about the replication instance types that can be created in the specified region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeOrderableReplicationInstances>`_


========
Synopsis
========

::

    describe-orderable-replication-instances
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

OrderableReplicationInstances -> (list)

  

  The order-able replication instances available.

  

  (structure)

    

    

    

    EngineVersion -> (string)

      

      The version of the replication engine.

      

      

    ReplicationInstanceClass -> (string)

      

      The compute and memory capacity of the replication instance.

       

      Valid Values: ``dms.t2.micro | dms.t2.small | dms.t2.medium | dms.t2.large | dms.c4.large | dms.c4.xlarge | dms.c4.2xlarge | dms.c4.4xlarge``  

      

      

    StorageType -> (string)

      

      The type of storage used by the replication instance.

      

      

    MinAllocatedStorage -> (integer)

      

      The minimum amount of storage (in gigabytes) that can be allocated for the replication instance.

      

      

    MaxAllocatedStorage -> (integer)

      

      The minimum amount of storage (in gigabytes) that can be allocated for the replication instance.

      

      

    DefaultAllocatedStorage -> (integer)

      

      The default amount of storage (in gigabytes) that is allocated for the replication instance.

      

      

    IncludedAllocatedStorage -> (integer)

      

      The amount of storage (in gigabytes) that is allocated for the replication instance.

      

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

