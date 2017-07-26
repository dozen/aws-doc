[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stack-events:


*********************
describe-stack-events
*********************



===========
Description
===========



Returns all stack related events for a specified stack. For more information about a stack's event history, go to `Stacks`_ in the AWS CloudFormation User Guide.

 

.. note::

  You can list events for stacks that have failed to create or have been deleted by specifying the unique stack identifier (stack ID).



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
  [--generate-cli-skeleton]




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

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

      

      

    Timestamp -> (timestamp)

      

      Time the status was updated.

      

      

    ResourceStatus -> (string)

      

      Current status of the resource.

      

      

    ResourceStatusReason -> (string)

      

      Success/failure message associated with the resource.

      

      

    ResourceProperties -> (string)

      

      BLOB of the properties used to create the resource.

      

      

    

  

NextToken -> (string)

  

  If the output exceeds 1 MB in size, a string that identifies the next page of events. If no additional page exists, this value is null.

  

  



.. _AWS Resource Types Reference: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html
.. _Stacks: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/concept-stack.html
