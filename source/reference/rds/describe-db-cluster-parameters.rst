[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-cluster-parameters:


******************************
describe-db-cluster-parameters
******************************



===========
Description
===========



Returns the detailed parameter list for a particular DB cluster parameter group. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    describe-db-cluster-parameters
  --db-cluster-parameter-group-name <value>
  [--source <value>]
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-cluster-parameter-group-name`` (string)


  The name of a specific DB cluster parameter group to return parameter details for. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--source`` (string)


  A value that indicates to return only parameters for a specific source. Parameter sources can be ``engine`` , ``service`` , or ``customer`` . 

  

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


  An optional pagination token provided by a previous ``describe-db-cluster-parameters`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Parameters -> (list)

  

  Provides a list of parameters for the DB cluster parameter group.

  

  (structure)

    

    This data type is used as a request parameter in the  modify-db-parameter-group and  reset-db-parameter-group actions. 

     

    This data type is used as a response element in the  describe-engine-default-parameters and  describe-db-parameters actions.

    

    ParameterName -> (string)

      

      Specifies the name of the parameter. 

      

      

    ParameterValue -> (string)

      

      Specifies the value of the parameter. 

      

      

    Description -> (string)

      

      Provides a description of the parameter. 

      

      

    Source -> (string)

      

      Indicates the source of the parameter value. 

      

      

    ApplyType -> (string)

      

      Specifies the engine specific parameters type. 

      

      

    DataType -> (string)

      

      Specifies the valid data type for the parameter. 

      

      

    AllowedValues -> (string)

      

      Specifies the valid range of values for the parameter. 

      

      

    IsModifiable -> (boolean)

      

      Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

      

      

    MinimumEngineVersion -> (string)

      

      The earliest engine version to which the parameter can apply. 

      

      

    ApplyMethod -> (string)

      

      Indicates when to apply parameter updates. 

      

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous describe-db-cluster-parameters request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  



.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
