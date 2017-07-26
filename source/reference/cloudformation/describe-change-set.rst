[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-change-set:


*******************
describe-change-set
*******************



===========
Description
===========



Returns the inputs for the change set and a list of changes that AWS CloudFormation will make if you execute the change set. For more information, see `Updating Stacks Using Change Sets <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-changesets.html>`_ in the AWS CloudFormation User Guide.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeChangeSet>`_


========
Synopsis
========

::

    describe-change-set
  --change-set-name <value>
  [--stack-name <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--change-set-name`` (string)


  The name or Amazon Resource Name (ARN) of the change set that you want to describe.

  

``--stack-name`` (string)


  If you specified the name of a change set, specify the stack name or ID (ARN) of the change set you want to describe.

  

``--next-token`` (string)


  A string (provided by the  describe-change-set response output) that identifies the next page of information that you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeSetName -> (string)

  

  The name of the change set.

  

  

ChangeSetId -> (string)

  

  The ARN of the change set.

  

  

StackId -> (string)

  

  The ARN of the stack that is associated with the change set.

  

  

StackName -> (string)

  

  The name of the stack that is associated with the change set.

  

  

Description -> (string)

  

  Information about the change set.

  

  

Parameters -> (list)

  

  A list of ``Parameter`` structures that describes the input parameters and their values used to create the change set. For more information, see the `Parameter <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html>`_ data type.

  

  (structure)

    

    The Parameter data type.

    

    ParameterKey -> (string)

      

      The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

      

      

    ParameterValue -> (string)

      

      The value associated with the parameter.

      

      

    UsePreviousValue -> (boolean)

      

      During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

      

      

    

  

CreationTime -> (timestamp)

  

  The start time when the change set was created, in UTC.

  

  

ExecutionStatus -> (string)

  

  If the change set execution status is ``AVAILABLE`` , you can execute the change set. If you can’t execute the change set, the status indicates why. For example, a change set might be in an ``UNAVAILABLE`` state because AWS CloudFormation is still creating it or in an ``OBSOLETE`` state because the stack was already updated.

  

  

Status -> (string)

  

  The current status of the change set, such as ``CREATE_IN_PROGRESS`` , ``CREATE_COMPLETE`` , or ``FAILED`` .

  

  

StatusReason -> (string)

  

  A description of the change set's status. For example, if your attempt to create a change set failed, AWS CloudFormation shows the error message.

  

  

NotificationARNs -> (list)

  

  The ARNs of the Amazon Simple Notification Service (Amazon SNS) topics that will be associated with the stack if you execute the change set.

  

  (string)

    

    

  

Capabilities -> (list)

  

  If you execute the change set, the list of capabilities that were explicitly acknowledged when the change set was created.

  

  (string)

    

    

  

Tags -> (list)

  

  If you execute the change set, the tags that will be associated with the stack.

  

  (structure)

    

    The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

    

    Key -> (string)

      

       *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

      

      

    Value -> (string)

      

       *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

      

      

    

  

Changes -> (list)

  

  A list of ``Change`` structures that describes the resources AWS CloudFormation changes if you execute the change set.

  

  (structure)

    

    The ``Change`` structure describes the changes AWS CloudFormation will perform if you execute the change set.

    

    Type -> (string)

      

      The type of entity that AWS CloudFormation changes. Currently, the only entity type is ``Resource`` .

      

      

    ResourceChange -> (structure)

      

      A ``ResourceChange`` structure that describes the resource and action that AWS CloudFormation will perform.

      

      Action -> (string)

        

        The action that AWS CloudFormation takes on the resource, such as ``Add`` (adds a new resource), ``Modify`` (changes a resource), or ``Remove`` (deletes a resource).

        

        

      LogicalResourceId -> (string)

        

        The resource's logical ID, which is defined in the stack's template.

        

        

      PhysicalResourceId -> (string)

        

        The resource's physical ID (resource name). Resources that you are adding don't have physical IDs because they haven't been created.

        

        

      ResourceType -> (string)

        

        The type of AWS CloudFormation resource, such as ``AWS::S3::Bucket`` .

        

        

      Replacement -> (string)

        

        For the ``Modify`` action, indicates whether AWS CloudFormation will replace the resource by creating a new one and deleting the old one. This value depends on the value of the ``RequiresRecreation`` property in the ``ResourceTargetDefinition`` structure. For example, if the ``RequiresRecreation`` field is ``Always`` and the ``Evaluation`` field is ``Static`` , ``Replacement`` is ``True`` . If the ``RequiresRecreation`` field is ``Always`` and the ``Evaluation`` field is ``Dynamic`` , ``Replacement`` is ``Conditionally`` .

         

        If you have multiple changes with different ``RequiresRecreation`` values, the ``Replacement`` value depends on the change with the most impact. A ``RequiresRecreation`` value of ``Always`` has the most impact, followed by ``Conditionally`` , and then ``Never`` .

        

        

      Scope -> (list)

        

        For the ``Modify`` action, indicates which resource attribute is triggering this update, such as a change in the resource attribute's ``Metadata`` , ``Properties`` , or ``Tags`` .

        

        (string)

          

          

        

      Details -> (list)

        

        For the ``Modify`` action, a list of ``ResourceChangeDetail`` structures that describes the changes that AWS CloudFormation will make to the resource. 

        

        (structure)

          

          For a resource with ``Modify`` as the action, the ``ResourceChange`` structure describes the changes AWS CloudFormation will make to that resource.

          

          Target -> (structure)

            

            A ``ResourceTargetDefinition`` structure that describes the field that AWS CloudFormation will change and whether the resource will be recreated.

            

            Attribute -> (string)

              

              Indicates which resource attribute is triggering this update, such as a change in the resource attribute's ``Metadata`` , ``Properties`` , or ``Tags`` .

              

              

            Name -> (string)

              

              If the ``Attribute`` value is ``Properties`` , the name of the property. For all other attributes, the value is null.

              

              

            RequiresRecreation -> (string)

              

              If the ``Attribute`` value is ``Properties`` , indicates whether a change to this property causes the resource to be recreated. The value can be ``Never`` , ``Always`` , or ``Conditionally`` . To determine the conditions for a ``Conditionally`` recreation, see the update behavior for that `property <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html>`_ in the AWS CloudFormation User Guide.

              

              

            

          Evaluation -> (string)

            

            Indicates whether AWS CloudFormation can determine the target value, and whether the target value will change before you execute a change set.

             

            For ``Static`` evaluations, AWS CloudFormation can determine that the target value will change, and its value. For example, if you directly modify the ``InstanceType`` property of an EC2 instance, AWS CloudFormation knows that this property value will change, and its value, so this is a ``Static`` evaluation.

             

            For ``Dynamic`` evaluations, cannot determine the target value because it depends on the result of an intrinsic function, such as a ``Ref`` or ``Fn::GetAtt`` intrinsic function, when the stack is updated. For example, if your template includes a reference to a resource that is conditionally recreated, the value of the reference (the physical ID of the resource) might change, depending on if the resource is recreated. If the resource is recreated, it will have a new physical ID, so all references to that resource will also be updated.

            

            

          ChangeSource -> (string)

            

            The group to which the ``CausingEntity`` value belongs. There are five entity groups:

             

             
            * ``ResourceReference`` entities are ``Ref`` intrinsic functions that refer to resources in the template, such as ``{ "Ref" : "MyEC2InstanceResource" }`` . 
             
            * ``ParameterReference`` entities are ``Ref`` intrinsic functions that get template parameter values, such as ``{ "Ref" : "MyPasswordParameter" }`` . 
             
            * ``ResourceAttribute`` entities are ``Fn::GetAtt`` intrinsic functions that get resource attribute values, such as ``{ "Fn::GetAtt" : [ "MyEC2InstanceResource", "PublicDnsName" ] }`` . 
             
            * ``DirectModification`` entities are changes that are made directly to the template. 
             
            * ``Automatic`` entities are ``AWS::CloudFormation::Stack`` resource types, which are also known as nested stacks. If you made no changes to the ``AWS::CloudFormation::Stack`` resource, AWS CloudFormation sets the ``ChangeSource`` to ``Automatic`` because the nested stack's template might have changed. Changes to a nested stack's template aren't visible to AWS CloudFormation until you run an update on the parent stack. 
             

            

            

          CausingEntity -> (string)

            

            The identity of the entity that triggered this change. This entity is a member of the group that is specified by the ``ChangeSource`` field. For example, if you modified the value of the ``KeyPairName`` parameter, the ``CausingEntity`` is the name of the parameter (``KeyPairName`` ).

             

            If the ``ChangeSource`` value is ``DirectModification`` , no value is given for ``CausingEntity`` .

            

            

          

        

      

    

  

NextToken -> (string)

  

  If the output exceeds 1 MB, a string that identifies the next page of changes. If there is no additional page, this value is null.

  

  

