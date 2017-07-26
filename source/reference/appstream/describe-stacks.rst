[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream describe-stacks:


***************
describe-stacks
***************



===========
Description
===========



If stack names are not provided, this operation describes the specified stacks; otherwise, all stacks in the account are described. To retrieve the next set of items, pass the ``nextToken`` value in a subsequent call to this operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/DescribeStacks>`_


========
Synopsis
========

::

    describe-stacks
  [--names <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--names`` (list)


  The stack names to describe. Use null to describe all the stacks for the AWS account.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The pagination token to use to retrieve the next page of results for this operation. If this value is null, it retrieves the first page.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Stacks -> (list)

  

  The list of stack details.

  

  (structure)

    

    Details about a stack.

    

    Arn -> (string)

      

      The ARN of the stack.

      

      

    Name -> (string)

      

      The unique identifier of the stack.

      

      

    Description -> (string)

      

      A meaningful description for the stack.

      

      

    DisplayName -> (string)

      

      A display name for the stack.

      

      

    CreatedTime -> (timestamp)

      

      The time stamp when the stack was created.

      

      

    StorageConnectors -> (list)

      

      The storage connectors to be enabled for the stack.

      

      (structure)

        

        Contains the parameters for a storage connector.

        

        ConnectorType -> (string)

          

          The type of storage connector. The possible values include: HOMEFOLDERS.

          

          

        ResourceIdentifier -> (string)

          

          The ARN associated with the storage connector.

          

          

        

      

    StackErrors -> (list)

      

      The list of errors associated with the stack.

      

      (structure)

        

        Contains the parameters for a stack error.

        

        ErrorCode -> (string)

          

          The error code of a stack error.

          

          

        ErrorMessage -> (string)

          

          The error message of a stack error.

          

          

        

      

    

  

NextToken -> (string)

  

  The pagination token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

