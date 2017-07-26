[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stack-events:


*********************
describe-stack-events
*********************



===========
Description
===========



Returns all stack related events for a specified stack in reverse chronological order. For more information about a stack's event history, go to `Stacks <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/concept-stack.html>`_ in the AWS CloudFormation User Guide.

 

.. note::

   

  You can list events for stacks that have failed to create or have been deleted by specifying the unique stack identifier (stack ID).

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeStackEvents>`_


``describe-stack-events`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``StackEvents``


========
Synopsis
========

::

    describe-stack-events
  [--stack-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

   

   
  * Running stacks: You can specify either the stack's name or its unique stack ID. 
   
  * Deleted stacks: You must specify the unique stack ID. 
   

   

  Default: There is no default value.

  

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

StackEvents -> (list)

  

  A list of ``StackEvents`` structures.

  

  (structure)

    

    The StackEvent data type.

    

    StackId -> (string)

      

      The unique ID name of the instance of the stack.

      

      

    EventId -> (string)

      

      The unique ID of this event.

      

      

    StackName -> (string)

      

      The name associated with a stack.

      

      

    LogicalResourceId -> (string)

      

      The logical name of the resource specified in the template.

      

      

    PhysicalResourceId -> (string)

      

      The name or unique identifier associated with the physical instance of the resource.

      

      

    ResourceType -> (string)

      

      Type of resource. (For more information, go to `AWS Resource Types Reference <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html>`_ in the AWS CloudFormation User Guide.)

      

      

    Timestamp -> (timestamp)

      

      Time the status was updated.

      

      

    ResourceStatus -> (string)

      

      Current status of the resource.

      

      

    ResourceStatusReason -> (string)

      

      Success/failure message associated with the resource.

      

      

    ResourceProperties -> (string)

      

      BLOB of the properties used to create the resource.

      

      

    ClientRequestToken -> (string)

      

      The token passed to the operation that generated this event.

       

      All events triggered by a given stack operation are assigned the same client request token, which you can use to track operations. For example, if you execute a ``create-stack`` operation with the token ``token1`` , then all the ``StackEvents`` generated by that operation will have ``ClientRequestToken`` set as ``token1`` .

       

      In the console, stack operations display the client request token on the Events tab. Stack operations that are initiated from the console use the token format *Console-StackOperation-ID* , which helps you easily identify the stack operation . For example, if you create a stack using the console, each stack event would be assigned the same token in the following format: ``Console-CreateStack-7f59c3cf-00d2-40c7-b2ff-e75db0987002`` . 

      

      

    

  

NextToken -> (string)

  

  If the output exceeds 1 MB in size, a string that identifies the next page of events. If no additional page exists, this value is null.

  

  

