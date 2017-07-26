[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-endpoint-types:


***********************
describe-endpoint-types
***********************



===========
Description
===========



Returns information about the type of endpoints available.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeEndpointTypes>`_


========
Synopsis
========

::

    describe-endpoint-types
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  Filters applied to the describe action.

   

  Valid filter names: engine-name | endpoint-type

  



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

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

SupportedEndpointTypes -> (list)

  

  The type of endpoints that are supported.

  

  (structure)

    

    

    

    EngineName -> (string)

      

      The database engine name. Valid values, depending on the EndPointType, include MYSQL, ORACLE, POSTGRES, MARIADB, AURORA, REDSHIFT, S3, SYBASE, DYNAMODB, MONGODB, and SQLSERVER.

      

      

    SupportsCDC -> (boolean)

      

      Indicates if Change Data Capture (CDC) is supported.

      

      

    EndpointType -> (string)

      

      The type of endpoint.

      

      

    

  

