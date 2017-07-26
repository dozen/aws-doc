[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation list-stack-set-operation-results:


********************************
list-stack-set-operation-results
********************************



===========
Description
===========



Returns summary information about the results of a stack set operation. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ListStackSetOperationResults>`_


========
Synopsis
========

::

    list-stack-set-operation-results
  --stack-set-name <value>
  --operation-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or unique ID of the stack set that you want to get operation results for.

  

``--operation-id`` (string)


  The ID of the stack set operation.

  

``--next-token`` (string)


  If the previous request didn't return all of the remaining results, the response object's ``next-token`` parameter value is set to a token. To retrieve the next set of results, call ``list-stack-set-operation-results`` again and assign that token to the request object's ``next-token`` parameter. If there are no remaining results, the previous response object's ``next-token`` parameter is set to ``null`` .

  

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

  

  A list of ``StackSetOperationResultSummary`` structures that contain information about the specified operation results, for accounts and regions that are included in the operation.

  

  (structure)

    

    The structure that contains information about a specified operation's results for a given account in a given region.

    

    Account -> (string)

      

      The name of the AWS account for this operation result.

      

      

    Region -> (string)

      

      The name of the AWS region for this operation result.

      

      

    Status -> (string)

      

      The result status of the stack set operation for the given account in the given region.

       

       
      * ``CANCELLED`` : The operation in the specified account and region has been cancelled. This is either because a user has stopped the stack set operation, or because the failure tolerance of the stack set operation has been exceeded. 
       
      * ``FAILED`` : The operation in the specified account and region failed.  If the stack set operation fails in enough accounts within a region, the failure tolerance for the stack set operation as a whole might be exceeded.  
       
      * ``RUNNING`` : The operation in the specified account and region is currently in progress. 
       
      * ``PENDING`` : The operation in the specified account and region has yet to start.  
       
      * ``SUCCEEDED`` : The operation in the specified account and region completed successfully. 
       

      

      

    StatusReason -> (string)

      

      The reason for the assigned result status.

      

      

    AccountGateResult -> (structure)

      

      The results of the account gate function AWS CloudFormation invokes, if present, before proceeding with stack set operations in an account

      

      Status -> (string)

        

        The status of the account gate function.

         

         
        * ``SUCCEEDED`` : The account gate function has determined that the account passes any requirements for stack set operations to occur. AWS CloudFormation proceeds with stack operations in the account.  
         
        * ``FAILED`` : The account gate function has determined that the account does not meet the requirements for stack set operations to occur. AWS CloudFormation cancels the stack set operations in that account, and the stack set operation status is set to FAILED. 
         
        * ``SKIPPED`` : An account gate function has not been specified for the account, or the AWSCloudFormationStackSetExecutionRole of the stack set adminstration account lacks permissions to invoke the function. AWS CloudFormation proceeds with stack set operations in the account.  
         

        

        

      StatusReason -> (string)

        

        The reason for the account gate status assigned to this account.

        

        

      

    

  

NextToken -> (string)

  

  If the request doesn't return all results, ``next-token`` is set to a token. To retrieve the next set of results, call ``ListOperationResults`` again and assign that token to the request object's ``next-token`` parameter. If there are no remaining results, ``next-token`` is set to ``null`` .

  

  

