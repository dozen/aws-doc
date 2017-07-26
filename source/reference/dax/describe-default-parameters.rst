[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax describe-default-parameters:


***************************
describe-default-parameters
***************************



===========
Description
===========



Returns the default system parameter information for the DAX caching software.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/DescribeDefaultParameters>`_


========
Synopsis
========

::

    describe-default-parameters
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

  

  

Parameters -> (list)

  

  A list of parameters. Each element in the list represents one parameter.

  

  (structure)

    

    Describes an individual setting that controls some aspect of DAX behavior.

    

    ParameterName -> (string)

      

      The name of the parameter.

      

      

    ParameterType -> (string)

      

      Determines whether the parameter can be applied to any nodes, or only nodes of a particular type.

      

      

    ParameterValue -> (string)

      

      The value for the parameter.

      

      

    NodeTypeSpecificValues -> (list)

      

      A list of node types, and specific parameter values for each node.

      

      (structure)

        

        Represents a parameter value that is applicable to a particular node type.

        

        NodeType -> (string)

          

          A node type to which the parameter value applies.

          

          

        Value -> (string)

          

          The parameter value for this node type.

          

          

        

      

    Description -> (string)

      

      A description of the parameter

      

      

    Source -> (string)

      

      How the parameter is defined. For example, ``system`` denotes a system-defined parameter.

      

      

    DataType -> (string)

      

      The data type of the parameter. For example, ``integer`` :

      

      

    AllowedValues -> (string)

      

      A range of values within which the parameter can be set.

      

      

    IsModifiable -> (string)

      

      Whether the customer is allowed to modify the parameter.

      

      

    ChangeType -> (string)

      

      The conditions under which changes to this parameter can be applied. For example, ``requires-reboot`` indicates that a new value for this parameter will only take effect if a node is rebooted.

      

      

    

  

