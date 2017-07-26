[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-source-regions:


***********************
describe-source-regions
***********************



===========
Description
===========



Returns a list of the source AWS regions where the current AWS region can create a Read Replica or copy a DB snapshot from. This API action supports pagination.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeSourceRegions>`_


========
Synopsis
========

::

    describe-source-regions
  [--region-name <value>]
  [--max-records <value>]
  [--marker <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--region-name`` (string)


  The source region name. For example, ``us-east-1`` .

   

  Constraints:

   

   
  * Must specify a valid AWS Region name. 
   

  

``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous  describe-source-regions request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` .

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

SourceRegions -> (list)

  

  A list of SourceRegion instances that contains each source AWS Region that the current region can get a Read Replica or a DB snapshot from.

  

  (structure)

    

    Contains an AWS Region name as the result of a successful call to the  describe-source-regions action.

    

    RegionName -> (string)

      

      The source region name.

      

      

    Endpoint -> (string)

      

      The source region endpoint.

      

      

    Status -> (string)

      

      The status of the source region.

      

      

    

  

