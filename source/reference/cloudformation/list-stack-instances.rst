[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation list-stack-instances:


********************
list-stack-instances
********************



===========
Description
===========



Returns summary information about stack instances that are associated with the specified stack set. You can filter for stack instances that are associated with a specific AWS account name or region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ListStackInstances>`_


========
Synopsis
========

::

    list-stack-instances
  --stack-set-name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--stack-instance-account <value>]
  [--stack-instance-region <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or unique ID of the stack set that you want to list stack instances for.

  

``--next-token`` (string)


  If the previous request didn't return all of the remaining results, the response's ``next-token`` parameter value is set to a token. To retrieve the next set of results, call ``list-stack-instances`` again and assign that token to the request object's ``next-token`` parameter. If there are no remaining results, the previous response object's ``next-token`` parameter is set to ``null`` .

  

``--max-results`` (integer)


  The maximum number of results to be returned with a single call. If the number of available results exceeds this maximum, the response includes a ``next-token`` value that you can assign to the ``next-token`` request parameter to get the next set of results.

  

``--stack-instance-account`` (string)


  The name of the AWS account that you want to list stack instances for.

  

``--stack-instance-region`` (string)


  The name of the region where you want to list stack instances. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Summaries -> (list)

  

  A list of ``StackInstanceSummary`` structures that contain information about the specified stack instances.

  

  (structure)

    

    The structure that contains summary information about a stack instance.

    

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

      

      The explanation for the specific status code assigned to this stack instance.

      

      

    

  

NextToken -> (string)

  

  If the request doesn't return all of the remaining results, ``next-token`` is set to a token. To retrieve the next set of results, call ``list-stack-instances`` again and assign that token to the request object's ``next-token`` parameter. If the request returns all results, ``next-token`` is set to ``null`` .

  

  

