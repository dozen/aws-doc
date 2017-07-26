[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-engine-default-parameters:


**********************************
describe-engine-default-parameters
**********************************



===========
Description
===========



The *describe-engine-default-parameters* action returns the default engine and system parameter information for the specified cache engine.



``describe-engine-default-parameters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EngineDefaults.Parameters``


========
Synopsis
========

::

    describe-engine-default-parameters
  --cache-parameter-group-family <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-parameter-group-family`` (string)


  The name of the cache parameter group family. Valid values are: ``memcached1.4`` | ``redis2.6`` | ``redis2.8`` 

  

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

  

  Represents the output of a *describe-engine-default-parameters* action.

  

  CacheParameterGroupFamily -> (string)

    

    Specifies the name of the cache parameter group family to which the engine default parameters apply.

    

    

  Marker -> (string)

    

    Provides an identifier to allow retrieval of paginated results.

    

    

  Parameters -> (list)

    

    Contains a list of engine default parameters.

    

    (structure)

      

      Describes an individual setting that controls some aspect of ElastiCache behavior.

      

      ParameterName -> (string)

        

        The name of the parameter.

        

        

      ParameterValue -> (string)

        

        The value of the parameter.

        

        

      Description -> (string)

        

        A description of the parameter.

        

        

      Source -> (string)

        

        The source of the parameter.

        

        

      DataType -> (string)

        

        The valid data type for the parameter.

        

        

      AllowedValues -> (string)

        

        The valid range of values for the parameter.

        

        

      IsModifiable -> (boolean)

        

        Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed.

        

        

      MinimumEngineVersion -> (string)

        

        The earliest cache engine version to which the parameter can apply.

        

        

      

    

  CacheNodeTypeSpecificParameters -> (list)

    

    A list of parameters specific to a particular cache node type. Each element in the list contains detailed information about one parameter.

    

    (structure)

      

      A parameter that has a different value for each cache node type it is applied to. For example, in a Redis cache cluster, a *cache.m1.large* cache node type would have a larger *maxmemory* value than a *cache.m1.small* type.

      

      ParameterName -> (string)

        

        The name of the parameter.

        

        

      Description -> (string)

        

        A description of the parameter.

        

        

      Source -> (string)

        

        The source of the parameter value.

        

        

      DataType -> (string)

        

        The valid data type for the parameter.

        

        

      AllowedValues -> (string)

        

        The valid range of values for the parameter.

        

        

      IsModifiable -> (boolean)

        

        Indicates whether (``true`` ) or not (``false`` ) the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed.

        

        

      MinimumEngineVersion -> (string)

        

        The earliest cache engine version to which the parameter can apply.

        

        

      CacheNodeTypeSpecificValues -> (list)

        

        A list of cache node types and their corresponding values for this parameter.

        

        (structure)

          

          A value that applies only to a certain cache node type.

          

          CacheNodeType -> (string)

            

            The cache node type for which this value applies.

            

            

          Value -> (string)

            

            The value for the cache node type.

            

            

          

        

      

    

  

