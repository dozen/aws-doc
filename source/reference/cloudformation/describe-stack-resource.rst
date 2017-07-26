[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stack-resource:


***********************
describe-stack-resource
***********************



===========
Description
===========



Returns a description of the specified resource in the specified stack.

 

For deleted stacks, describe-stack-resource returns resource information for up to 90 days after the stack has been deleted.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeStackResource>`_


========
Synopsis
========

::

    describe-stack-resource
  --stack-name <value>
  --logical-resource-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

   

   
  * Running stacks: You can specify either the stack's name or its unique stack ID. 
   
  * Deleted stacks: You must specify the unique stack ID. 
   

   

  Default: There is no default value.

  

``--logical-resource-id`` (string)


  The logical name of the resource as specified in the template.

   

  Default: There is no default value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StackResourceDetail -> (structure)

  

  A ``StackResourceDetail`` structure containing the description of the specified resource in the specified stack.

  

  StackName -> (string)

    

    The name associated with the stack.

    

    

  StackId -> (string)

    

    Unique identifier of the stack.

    

    

  LogicalResourceId -> (string)

    

    The logical name of the resource specified in the template.

    

    

  PhysicalResourceId -> (string)

    

    The name or unique identifier that corresponds to a physical instance ID of a resource supported by AWS CloudFormation.

    

    

  ResourceType -> (string)

    

    Type of resource. ((For more information, go to `AWS Resource Types Reference <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html>`_ in the AWS CloudFormation User Guide.)

    

    

  LastUpdatedTimestamp -> (timestamp)

    

    Time the status was updated.

    

    

  ResourceStatus -> (string)

    

    Current status of the resource.

    

    

  ResourceStatusReason -> (string)

    

    Success/failure message associated with the resource.

    

    

  Description -> (string)

    

    User defined description associated with the resource.

    

    

  Metadata -> (string)

    

    The content of the ``Metadata`` attribute declared for the resource. For more information, see `Metadata Attribute <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-attribute-metadata.html>`_ in the AWS CloudFormation User Guide.

    

    

  

