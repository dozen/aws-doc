[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-engine-versions:


***************************
describe-db-engine-versions
***************************



===========
Description
===========



Returns a list of the available DB engines.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeDBEngineVersions>`_


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
  [--list-supported-timezones | --no-list-supported-timezones]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




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


  If this parameter is specified and the requested engine supports the ``CharacterSetName`` parameter for ``create-db-instance`` , the response includes a list of supported character sets for each engine version. 

  

``--list-supported-timezones`` | ``--no-list-supported-timezones`` (boolean)


  If this parameter is specified and the requested engine supports the ``TimeZone`` parameter for ``create-db-instance`` , the response includes a list of supported time zones for each engine version. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      A list of the character sets supported by this engine for the ``CharacterSetName`` parameter of the ``create-db-instance`` action. 

      

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

          

          

        

      

    SupportedTimezones -> (list)

      

      A list of the time zones supported by this engine for the ``Timezone`` parameter of the ``create-db-instance`` action. 

      

      (structure)

        

        A time zone associated with a  DBInstance or a  DBSnapshot . This data type is an element in the response to the  describe-db-instances , the  describe-db-snapshots , and the  describe-db-engine-versions actions. 

        

        TimezoneName -> (string)

          

          The name of the time zone.

          

          

        

      

    

  

