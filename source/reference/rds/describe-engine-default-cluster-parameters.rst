[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-engine-default-cluster-parameters:


******************************************
describe-engine-default-cluster-parameters
******************************************



===========
Description
===========



Returns the default engine and system parameter information for the cluster database engine. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    describe-engine-default-cluster-parameters
  --db-parameter-group-family <value>
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-parameter-group-family`` (string)


  The name of the DB cluster parameter group family to return engine parameter information for. 

  

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


  An optional pagination token provided by a previous ``describe-engine-default-cluster-parameters`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EngineDefaults -> (structure)

  

  Contains the result of a successful invocation of the  describe-engine-default-parameters action. 

  

  DBParameterGroupFamily -> (string)

    

    Specifies the name of the DB parameter group family that the engine default parameters apply to. 

    

    

  Marker -> (string)

    

    An optional pagination token provided by a previous EngineDefaults request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

    

    

  Parameters -> (list)

    

    Contains a list of engine default parameters. 

    

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

        

        

      

    

  



.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
