[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation list-stack-set-operations:


*************************
list-stack-set-operations
*************************



===========
Description
===========



Returns summary information about operations performed on a stack set. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ListStackSetOperations>`_


========
Synopsis
========

::

    list-stack-set-operations
  --stack-set-name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or unique ID of the stack set that you want to get operation summaries for.

  

``--next-token`` (string)


  If the previous paginated request didn't return all of the remaining results, the response object's ``next-token`` parameter value is set to a token. To retrieve the next set of results, call ``list-stack-set-operations`` again and assign that token to the request object's ``next-token`` parameter. If there are no remaining results, the previous response object's ``next-token`` parameter is set to ``null`` .

  

``--max-results`` (integer)


  The maximum number of results to be returned with a single call. If the number of available results exceeds this maximum, the response includes a ``next-token`` value that you can assign to the ``next-token`` request parameter to get the next set of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Summaries -> (list)

  

  A list of ``StackSetOperationSummary`` structures that contain summary information about operations for the specified stack set.

  

  (structure)

    

    The structures that contain summary information about the specified operation.

    

    OperationId -> (string)

      

      The unique ID of the stack set operation.

      

      

    Action -> (string)

      

      The type of operation: ``CREATE`` , ``UPDATE`` , or ``DELETE`` . Create and delete operations affect only the specified stack instances that are associated with the specified stack set. Update operations affect both the stack set itself as well as *all* associated stack set instances.

      

      

    Status -> (string)

      

      The overall status of the operation.

       

       
      * ``FAILED`` : The operation exceeded the specified failure tolerance. The failure tolerance value that you've set for an operation is applied for each region during stack create and update operations. If the number of failed stacks within a region exceeds the failure tolerance, the status of the operation in the region is set to ``FAILED`` . This in turn sets the status of the operation as a whole to ``FAILED`` , and AWS CloudFormation cancels the operation in any remaining regions. 
       
      * ``RUNNING`` : The operation is currently being performed. 
       
      * ``STOPPED`` : The user has cancelled the operation. 
       
      * ``STOPPING`` : The operation is in the process of stopping, at user request.  
       
      * ``SUCCEEDED`` : The operation completed creating or updating all the specified stacks without exceeding the failure tolerance for the operation. 
       

      

      

    CreationTimestamp -> (timestamp)

      

      The time at which the operation was initiated. Note that the creation times for the stack set operation might differ from the creation time of the individual stacks themselves. This is because AWS CloudFormation needs to perform preparatory work for the operation, such as dispatching the work to the requested regions, before actually creating the first stacks.

      

      

    EndTimestamp -> (timestamp)

      

      The time at which the stack set operation ended, across all accounts and regions specified. Note that this doesn't necessarily mean that the stack set operation was successful, or even attempted, in each account or region.

      

      

    

  

NextToken -> (string)

  

  If the request doesn't return all results, ``next-token`` is set to a token. To retrieve the next set of results, call ``ListOperationResults`` again and assign that token to the request object's ``next-token`` parameter. If there are no remaining results, ``next-token`` is set to ``null`` .

  

  

