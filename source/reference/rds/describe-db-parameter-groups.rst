[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-parameter-groups:


****************************
describe-db-parameter-groups
****************************



===========
Description
===========



Returns a list of ``DBParameterGroup`` descriptions. If a ``DBParameterGroupName`` is specified, the list will contain only the description of the specified DB parameter group. 



``describe-db-parameter-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DBParameterGroups``


========
Synopsis
========

::

    describe-db-parameter-groups
  [--db-parameter-group-name <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-parameter-group-name`` (string)


  The name of a specific DB parameter group to return details for. 

   

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

  

  

DBParameterGroups -> (list)

  

  A list of  DBParameterGroup instances. 

  

  (structure)

    

    Contains the result of a successful invocation of the  create-db-parameter-group action. 

     

    This data type is used as a request parameter in the  delete-db-parameter-group action, and as a response element in the  describe-db-parameter-groups action. 

    

    DBParameterGroupName -> (string)

      

      Provides the name of the DB parameter group. 

      

      

    DBParameterGroupFamily -> (string)

      

      Provides the name of the DB parameter group family that this DB parameter group is compatible with. 

      

      

    Description -> (string)

      

      Provides the customer-specified description for this DB parameter group. 

      

      

    

  

