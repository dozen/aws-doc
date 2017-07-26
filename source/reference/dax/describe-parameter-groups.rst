[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax describe-parameter-groups:


*************************
describe-parameter-groups
*************************



===========
Description
===========



Returns a list of parameter group descriptions. If a parameter group name is specified, the list will contain only the descriptions for that group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/DescribeParameterGroups>`_


========
Synopsis
========

::

    describe-parameter-groups
  [--parameter-group-names <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--parameter-group-names`` (list)


  The names of the parameter groups.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to include in the response. If more results exist than the specified ``MaxResults`` value, a token is included in the response so that the remaining results can be retrieved.

   

  The value for ``MaxResults`` must be between 20 and 100.

  

``--next-token`` (string)


  An optional token returned from a prior request. Use this token for pagination of results from this action. If this parameter is specified, the response includes only results beyond the token, up to the value specified by ``MaxResults`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextToken -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

ParameterGroups -> (list)

  

  An array of parameter groups. Each element in the array represents one parameter group.

  

  (structure)

    

    A named set of parameters that are applied to all of the nodes in a DAX cluster.

    

    ParameterGroupName -> (string)

      

      The name of the parameter group.

      

      

    Description -> (string)

      

      A description of the parameter group.

      

      

    

  

