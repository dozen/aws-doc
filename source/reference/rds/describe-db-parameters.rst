[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-parameters:


**********************
describe-db-parameters
**********************



===========
Description
===========



Returns the detailed parameter list for a particular DB parameter group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeDBParameters>`_


``describe-db-parameters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Parameters``


========
Synopsis
========

::

    describe-db-parameters
  --db-parameter-group-name <value>
  [--source <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-parameter-group-name`` (string)


  The name of a specific DB parameter group to return details for.

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--source`` (string)


  The parameter types to return.

   

  Default: All parameter types returned

   

  Valid Values: ``user | system | engine-default``  

  

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

Parameters -> (list)

  

  A list of  Parameter values. 

  

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

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

