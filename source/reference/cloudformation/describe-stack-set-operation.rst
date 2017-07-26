[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stack-set-operation:


****************************
describe-stack-set-operation
****************************



===========
Description
===========



Returns the description of the specified stack set operation. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeStackSetOperation>`_


========
Synopsis
========

::

    describe-stack-set-operation
  --stack-set-name <value>
  --operation-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or the unique stack ID of the stack set for the stack operation.

  

``--operation-id`` (string)


  The unique ID of the stack set operation. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StackSetOperation -> (structure)

  

  The specified stack set operation.

  

  OperationId -> (string)

    

    The unique ID of a stack set operation.

    

    

  StackSetId -> (string)

    

    The ID of the stack set.

    

    

  Action -> (string)

    

    The type of stack set operation: ``CREATE`` , ``UPDATE`` , or ``DELETE`` . Create and delete operations affect only the specified stack set instances that are associated with the specified stack set. Update operations affect both the stack set itself, as well as *all* associated stack set instances.

    

    

  Status -> (string)

    

    The status of the operation. 

     

     
    * ``FAILED`` : The operation exceeded the specified failure tolerance. The failure tolerance value that you've set for an operation is applied for each region during stack create and update operations. If the number of failed stacks within a region exceeds the failure tolerance, the status of the operation in the region is set to ``FAILED`` . This in turn sets the status of the operation as a whole to ``FAILED`` , and AWS CloudFormation cancels the operation in any remaining regions. 
     
    * ``RUNNING`` : The operation is currently being performed. 
     
    * ``STOPPED`` : The user has cancelled the operation. 
     
    * ``STOPPING`` : The operation is in the process of stopping, at user request.  
     
    * ``SUCCEEDED`` : The operation completed creating or updating all the specified stacks without exceeding the failure tolerance for the operation. 
     

    

    

  OperationPreferences -> (structure)

    

    The preferences for how AWS CloudFormation performs this stack set operation.

    

    RegionOrder -> (list)

      

      The order of the regions in where you want to perform the stack operation.

      

      (string)

        

        

      

    FailureToleranceCount -> (integer)

      

      The number of accounts, per region, for which this operation can fail before AWS CloudFormation stops the operation in that region. If the operation is stopped in a region, AWS CloudFormation doesn't attempt the operation in any subsequent regions.

       

      Conditional: You must specify either ``FailureToleranceCount`` or ``FailureTolerancePercentage`` (but not both).

      

      

    FailureTolerancePercentage -> (integer)

      

      The percentage of accounts, per region, for which this stack operation can fail before AWS CloudFormation stops the operation in that region. If the operation is stopped in a region, AWS CloudFormation doesn't attempt the operation in any subsequent regions.

       

      When calculating the number of accounts based on the specified percentage, AWS CloudFormation rounds *down* to the next whole number.

       

      Conditional: You must specify either ``FailureToleranceCount`` or ``FailureTolerancePercentage`` , but not both.

      

      

    MaxConcurrentCount -> (integer)

      

      The maximum number of accounts in which to perform this operation at one time. This is dependent on the value of ``FailureToleranceCount`` —``MaxConcurrentCount`` is at most one more than the ``FailureToleranceCount`` .

       

      Conditional: You must specify either ``MaxConcurrentCount`` or ``MaxConcurrentPercentage`` , but not both.

      

      

    MaxConcurrentPercentage -> (integer)

      

      The maximum percentage of accounts in which to perform this operation at one time.

       

      When calculating the number of accounts based on the specified percentage, AWS CloudFormation rounds down to the next whole number. This is true except in cases where rounding down would result is zero. In this case, CloudFormation sets the number as one instead.

       

      Conditional: You must specify either ``MaxConcurrentCount`` or ``MaxConcurrentPercentage`` , but not both.

      

      

    

  RetainStacks -> (boolean)

    

    For stack set operations of action type ``DELETE`` , specifies whether to remove the stack instances from the specified stack set, but doesn't delete the stacks. You can't reassociate a retained stack, or add an existing, saved stack to a new stack set.

    

    

  CreationTimestamp -> (timestamp)

    

    The time at which the operation was initiated. Note that the creation times for the stack set operation might differ from the creation time of the individual stacks themselves. This is because AWS CloudFormation needs to perform preparatory work for the operation, such as dispatching the work to the requested regions, before actually creating the first stacks.

    

    

  EndTimestamp -> (timestamp)

    

    The time at which the stack set operation ended, across all accounts and regions specified. Note that this doesn't necessarily mean that the stack set operation was successful, or even attempted, in each account or region.

    

    

  

