[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-engine-default-parameters:


**********************************
describe-engine-default-parameters
**********************************



===========
Description
===========



Returns the default engine and system parameter information for the specified database engine. 



``describe-engine-default-parameters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EngineDefaults.Parameters``


========
Synopsis
========

::

    describe-engine-default-parameters
  --db-parameter-group-family <value>
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-parameter-group-family`` (string)


  The name of the DB parameter group family. 

  

``--filters`` (list)


  Not currently supported. 

  



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

        

        

      

    

  

