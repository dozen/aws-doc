[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation list-exports:


************
list-exports
************



===========
Description
===========



Lists all exported output values in the account and region in which you call this action. Use this action to see the exported output values that you can import into other stacks. To import values, use the ` ``Fn::ImportValue`` http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-importvalue.html`_ function. 

 

For more information, see `AWS CloudFormation Export Stack Output Values <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-stack-exports.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ListExports>`_


``list-exports`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Exports``


========
Synopsis
========

::

    list-exports
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Exports -> (list)

  

  The output for the  list-exports action.

  

  (structure)

    

    The ``Export`` structure describes the exported output values for a stack.

    

    ExportingStackId -> (string)

      

      The stack that contains the exported output name and value.

      

      

    Name -> (string)

      

      The name of exported output value. Use this name and the ``Fn::ImportValue`` function to import the associated value into other stacks. The name is defined in the ``Export`` field in the associated stack's ``Outputs`` section.

      

      

    Value -> (string)

      

      The value of the exported output, such as a resource physical ID. This value is defined in the ``Export`` field in the associated stack's ``Outputs`` section.

      

      

    

  

NextToken -> (string)

  

  If the output exceeds 100 exported output values, a string that identifies the next page of exports. If there is no additional page, this value is null.

  

  



.. _http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-importvalue.html: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-importvalue.html
