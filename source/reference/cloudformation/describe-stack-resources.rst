[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stack-resources:


************************
describe-stack-resources
************************



===========
Description
===========



Returns AWS resource descriptions for running and deleted stacks. If ``stack-name`` is specified, all the associated resources that are part of the stack are returned. If ``physical-resource-id`` is specified, the associated resources of the stack that the resource belongs to are returned.

 

.. note::

  Only the first 100 resources will be returned. If your stack has more resources than this, you should use ``list-stack-resources`` instead.

 

For deleted stacks, ``describe-stack-resources`` returns resource information for up to 90 days after the stack has been deleted.

 

You must specify either ``stack-name`` or ``physical-resource-id`` , but not both. In addition, you can specify ``logical-resource-id`` to filter the returned result. For more information about resources, the ``logical-resource-id`` and ``physical-resource-id`` , go to the `AWS CloudFormation User Guide`_ .

 

.. note::

  A ``ValidationError`` is returned if you specify both ``stack-name`` and ``physical-resource-id`` in the same request.



========
Synopsis
========

::

    describe-stack-resources
  [--stack-name <value>]
  [--logical-resource-id <value>]
  [--physical-resource-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

   

   
  * Running stacks: You can specify either the stack's name or its unique stack ID.
   
  * Deleted stacks: You must specify the unique stack ID.
   

   

  Default: There is no default value.

   

  Required: Conditional. If you do not specify ``stack-name`` , you must specify ``physical-resource-id`` .

  

``--logical-resource-id`` (string)


  The logical name of the resource as specified in the template.

   

  Default: There is no default value.

  

``--physical-resource-id`` (string)


  The name or unique identifier that corresponds to a physical instance ID of a resource supported by AWS CloudFormation.

   

  For example, for an Amazon Elastic Compute Cloud (EC2) instance, ``physical-resource-id`` corresponds to the ``InstanceId`` . You can pass the EC2 ``InstanceId`` to ``describe-stack-resources`` to find which stack the instance belongs to and what other resources are part of the stack.

   

  Required: Conditional. If you do not specify ``physical-resource-id`` , you must specify ``stack-name`` .

   

  Default: There is no default value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

StackResources -> (list)

  

  A list of ``StackResource`` structures.

  

  (structure)

    

    The StackResource data type.

    

    StackName -> (string)

      

      The name associated with the stack.

      

      

    StackId -> (string)

      

      Unique identifier of the stack.

      

      

    LogicalResourceId -> (string)

      

      The logical name of the resource specified in the template.

      

      

    PhysicalResourceId -> (string)

      

      The name or unique identifier that corresponds to a physical instance ID of a resource supported by AWS CloudFormation.

      

      

    ResourceType -> (string)

      

      Type of resource. (For more information, go to `AWS Resource Types Reference`_ in the AWS CloudFormation User Guide.)

      

      

    Timestamp -> (timestamp)

      

      Time the status was updated.

      

      

    ResourceStatus -> (string)

      

      Current status of the resource.

      

      

    ResourceStatusReason -> (string)

      

      Success/failure message associated with the resource.

      

      

    Description -> (string)

      

      User defined description associated with the resource.

      

      

    

  



.. _AWS Resource Types Reference: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html
.. _AWS CloudFormation User Guide: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/
