[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-parameters:


*******************
describe-parameters
*******************



===========
Description
===========



Get information about a parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeParameters>`_


``describe-parameters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Parameters``


========
Synopsis
========

::

    describe-parameters
  [--filters <value>]
  [--parameter-filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters. Use a filter to return a more specific list of results.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "Name"|"Type"|"KeyId",
      "Values": ["string", ...]
    }
    ...
  ]



``--parameter-filters`` (list)


  Filters to limit the request results.

  



Shorthand Syntax::

    Key=string,Option=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Option": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list all Parameters**

This example lists all parameters.

Command::

  aws ssm describe-parameters
  
Output::

  {
    "Parameters": [
        {
            "LastModifiedUser": "arn:aws:iam::809632081692:user/admin",
            "LastModifiedDate": 1487880325.324,
            "Type": "String",
            "Name": "welcome"
        }
    ]
  }

**To list all Parameters matching specific metadata**

This example lists all parameters matching a filter.

Command::

  aws ssm describe-parameters --filters "Key=Name,Values=helloWorld"


======
Output
======

Parameters -> (list)

  

  Parameters returned by the request.

  

  (structure)

    

    Metada includes information like the ARN of the last user and the date/time the parameter was last used.

    

    Name -> (string)

      

      The parameter name.

      

      

    Type -> (string)

      

      The type of parameter. Valid parameter types include the following: String, String list, Secure string.

      

      

    KeyId -> (string)

      

      The ID of the query key used for this parameter.

      

      

    LastModifiedDate -> (timestamp)

      

      Date the parameter was last changed or updated.

      

      

    LastModifiedUser -> (string)

      

      Amazon Resource Name (ARN) of the AWS user who last changed the parameter.

      

      

    Description -> (string)

      

      Description of the parameter actions.

      

      

    AllowedPattern -> (string)

      

      A parameter name can include only the following letters and symbols.

       

      a-zA-Z0-9_.-

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

