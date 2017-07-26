[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stack-instance:


***********************
describe-stack-instance
***********************



===========
Description
===========



Returns the stack instance that's associated with the specified stack set, AWS account, and region.

 

For a list of stack instances that are associated with a specific stack set, use  list-stack-instances .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeStackInstance>`_


========
Synopsis
========

::

    describe-stack-instance
  --stack-set-name <value>
  --stack-instance-account <value>
  --stack-instance-region <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or the unique stack ID of the stack set that you want to get stack instance information for.

  

``--stack-instance-account`` (string)


  The ID of an AWS account that's associated with this stack instance.

  

``--stack-instance-region`` (string)


  The name of a region that's associated with this stack instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StackInstance -> (structure)

  

  The stack instance that matches the specified request parameters.

  

  StackSetId -> (string)

    

    The name or unique ID of the stack set that the stack instance is associated with.

    

    

  Region -> (string)

    

    The name of the AWS region that the stack instance is associated with.

    

    

  Account -> (string)

    

    The name of the AWS account that the stack instance is associated with.

    

    

  StackId -> (string)

    

    The ID of the stack instance.

    

    

  Status -> (string)

    

    The status of the stack instance, in terms of its synchronization with its associated stack set.

     

     
    * ``INOPERABLE`` : A ``delete-stack-instances`` operation has failed and left the stack in an unstable state. Stacks in this state are excluded from further ``update-stack-set`` and ``delete-stack-instances`` operations. You might need to clean up the stack manually. 
     
    * ``OUTDATED`` : The stack isn't currently up to date with the stack set because: 

       
      * The associated stack failed during a ``create-stack-set`` or ``update-stack-set`` operation.  
       
      * The stack was part of a ``create-stack-set`` or ``update-stack-set`` operation that failed or was stopped before the stack was created or updated.  
       

     
     
    * ``CURRENT`` : The stack is currently up to date with the stack set. 
     

    

    

  StatusReason -> (string)

    

    The explanation for the specific status code that is assigned to this stack instance.

    

    

  

