[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-cluster-parameter-groups:


************************************
describe-db-cluster-parameter-groups
************************************



===========
Description
===========



Returns a list of ``DBClusterParameterGroup`` descriptions. If a ``DBClusterParameterGroupName`` parameter is specified, the list will contain only the description of the specified DB cluster parameter group. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    describe-db-cluster-parameter-groups
  [--db-cluster-parameter-group-name <value>]
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-cluster-parameter-group-name`` (string)


  The name of a specific DB cluster parameter group to return details for. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

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



``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous ``describe-db-cluster-parameter-groups`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous ``describe-db-cluster-parameter-groups`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

DBClusterParameterGroups -> (list)

  

  A list of DB cluster parameter groups.

  

  (structure)

    

    Contains the result of a successful invocation of the  create-db-cluster-parameter-group action. 

     

    This data type is used as a request parameter in the  delete-db-cluster-parameter-group action, and as a response element in the  describe-db-cluster-parameter-groups action. 

    

    DBClusterParameterGroupName -> (string)

      

      Provides the name of the DB cluster parameter group. 

      

      

    DBParameterGroupFamily -> (string)

      

      Provides the name of the DB parameter group family that this DB cluster parameter group is compatible with. 

      

      

    Description -> (string)

      

      Provides the customer-specified description for this DB cluster parameter group. 

      

      

    

  



.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
