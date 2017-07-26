[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-engine-versions:


***************************
describe-db-engine-versions
***************************



===========
Description
===========



Returns a list of the available DB engines. 



``describe-db-engine-versions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DBEngineVersions``


========
Synopsis
========

::

    describe-db-engine-versions
  [--engine <value>]
  [--engine-version <value>]
  [--db-parameter-group-family <value>]
  [--filters <value>]
  [--default-only | --no-default-only]
  [--list-supported-character-sets | --no-list-supported-character-sets]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--engine`` (string)


  The database engine to return. 

  

``--engine-version`` (string)


  The database engine version to return. 

   

  Example: ``5.1.49`` 

  

``--db-parameter-group-family`` (string)


  The name of a specific DB parameter group family to return details for. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

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



``--default-only`` | ``--no-default-only`` (boolean)


  Indicates that only the default version of the specified engine or engine and major version combination is returned. 

  

``--list-supported-character-sets`` | ``--no-list-supported-character-sets`` (boolean)


  If this parameter is specified, and if the requested engine supports the CharacterSetName parameter for CreateDBInstance, the response includes a list of supported character sets for each engine version. 

  

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

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

DBEngineVersions -> (list)

  

  A list of ``DBEngineVersion`` elements. 

  

  (structure)

    

    This data type is used as a response element in the action  describe-db-engine-versions . 

    

    Engine -> (string)

      

      The name of the database engine. 

      

      

    EngineVersion -> (string)

      

      The version number of the database engine. 

      

      

    DBParameterGroupFamily -> (string)

      

      The name of the DB parameter group family for the database engine. 

      

      

    DBEngineDescription -> (string)

      

      The description of the database engine. 

      

      

    DBEngineVersionDescription -> (string)

      

      The description of the database engine version. 

      

      

    DefaultCharacterSet -> (structure)

      

      The default character set for new instances of this engine version, if the ``CharacterSetName`` parameter of the create-db-instance API is not specified. 

      

      CharacterSetName -> (string)

        

        The name of the character set. 

        

        

      CharacterSetDescription -> (string)

        

        The description of the character set. 

        

        

      

    SupportedCharacterSets -> (list)

      

      A list of the character sets supported by this engine for the ``CharacterSetName`` parameter of the create-db-instance API. 

      

      (structure)

        

        This data type is used as a response element in the action  describe-db-engine-versions . 

        

        CharacterSetName -> (string)

          

          The name of the character set. 

          

          

        CharacterSetDescription -> (string)

          

          The description of the character set. 

          

          

        

      

    ValidUpgradeTarget -> (list)

      

      A list of engine versions that this database engine version can be upgraded to.

      

      (structure)

        

        The version of the database engine that a DB instance can be upgraded to.

        

        Engine -> (string)

          

          The name of the upgrade target database engine. 

          

          

        EngineVersion -> (string)

          

          The version number of the upgrade target database engine.

          

          

        Description -> (string)

          

          The version of the database engine that a DB instance can be upgraded to.

          

          

        AutoUpgrade -> (boolean)

          

          A value that indicates whether the target version will be applied to any source DB instances that have AutoMinorVersionUpgrade set to true.

          

          

        IsMajorVersionUpgrade -> (boolean)

          

          A value that indicates whether a database engine will be upgraded to a major version.

          

          

        

      

    

  

