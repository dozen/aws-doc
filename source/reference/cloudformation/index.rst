[ :ref:`aws <cli:aws>` ]

.. _cli:aws cloudformation:


**************
cloudformation
**************



===========
Description
===========

 

AWS CloudFormation allows you to create and manage AWS infrastructure deployments predictably and repeatedly. You can use AWS CloudFormation to leverage AWS products, such as Amazon Elastic Compute Cloud, Amazon Elastic Block Store, Amazon Simple Notification Service, Elastic Load Balancing, and Auto Scaling to build highly-reliable, highly scalable, cost-effective applications without creating or configuring the underlying AWS infrastructure.

 

With AWS CloudFormation, you declare all of your resources and dependencies in a template file. The template defines a collection of resources as a single unit called a stack. AWS CloudFormation creates and deletes all member resources of the stack together and manages all dependencies between the resources for you.

 

For more information about AWS CloudFormation, see the `AWS CloudFormation Product Page <http://aws.amazon.com/cloudformation/>`_ .

 

Amazon CloudFormation makes use of other AWS products. If you need additional technical information about a specific AWS product, you can find the product's technical documentation at `docs.aws.amazon.com <http://docs.aws.amazon.com/>`_ .

 

 *APIs for stacks*  

 

When you use AWS CloudFormation, you manage related resources as a single unit called a stack. You create, update, and delete a collection of resources by creating, updating, and deleting stacks. All the resources in a stack are defined by the stack's AWS CloudFormation template. 

 

Actions

 

 
* `cancel-update-stack <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_CancelUpdateStack.html>`_   
 
* `continue-update-rollback <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ContinueUpdateRollback.html>`_   
 
* `create-stack <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_CreateStack.html>`_   
 
* `delete-stack <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DeleteStack.html>`_   
 
* `describe-stack-events <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeStackEvents.html>`_   
 
* `describe-stack-resource <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeStackResource.html>`_   
 
* `describe-stack-resources <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeStackResources.html>`_   
 
* `describe-stacks <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeStacks.html>`_   
 
* `estimate-template-cost <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_EstimateTemplateCost.html>`_   
 
* `get-stack-policy <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_GetStackPolicy.html>`_   
 
* `get-template <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_GetTemplate.html>`_   
 
* `get-template-summary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_GetTemplateSummary.html>`_   
 
* `list-exports <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListExports.html>`_   
 
* `list-imports <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListImports.html>`_   
 
* `list-stack-resources <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListStackResources.html>`_   
 
* `list-stacks <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListStacks.html>`_   
 
* `set-stack-policy <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_SetStackPolicy.html>`_   
 
* `update-stack <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_UpdateStack.html>`_   
 
* `validate-template <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ValidateTemplate.html>`_   
 

 

Data Types

 

 
* `Export <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Export.html>`_   
 
* `Parameter <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html>`_   
 
* `ParameterConstraints <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ParameterConstraints.html>`_   
 
* `ParameterDeclaration <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ParameterDeclaration.html>`_   
 
* `Stack <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Stack.html>`_   
 
* `StackEvent <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackEvent.html>`_   
 
* `StackResource <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackResource.html>`_   
 
* `StackResourceDetail <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackResourceDetail.html>`_   
 
* `StackResourceSummary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackResourceSummary.html>`_   
 
* `StackSummary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSummary.html>`_   
 
* `Tag <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Tag.html>`_   
 
* `TemplateParameter <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_TemplateParameter.html>`_   
 

 

 *APIs for change sets*  

 

If you need to make changes to the running resources in a stack, you update the stack. Before making changes to your resources, you can generate a change set, which is summary of your proposed changes. Change sets allow you to see how your changes might impact your running resources, especially for critical resources, before implementing them.

 

Actions

 

 
* `create-change-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_CreateChangeSet.html>`_   
 
* `delete-change-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DeleteChangeSet.html>`_   
 
* `describe-change-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeChangeSet.html>`_   
 
* `execute-change-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ExecuteChangeSet.html>`_   
 
* `list-change-sets <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListChangeSets.html>`_   
 

 

Data Types

 

 
* `Change <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Change.html>`_   
 
* `ChangeSetSummary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ChangeSetSummary.html>`_   
 
* `ResourceChange <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ResourceChange.html>`_   
 
* `ResourceChangeDetail <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ResourceChangeDetail.html>`_   
 
* `ResourceTargetDefinition <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ResourceTargetDefinition.html>`_   
 

 

 *APIs for stack sets*  

 

AWS CloudFormation StackSets lets you create a collection, or stack set, of stacks that can automatically and safely provision a common set of AWS resources across multiple AWS accounts and multiple AWS regions from a single AWS CloudFormation template. When you create a stack set, AWS CloudFormation provisions a stack in each of the specified accounts and regions by using the supplied AWS CloudFormation template and parameters. Stack sets let you manage a common set of AWS resources in a selection of accounts and regions in a single operation. 

 

Actions

 

 
* `create-stack-instances <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_CreateStackInstances.html>`_   
 
* `create-stack-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_CreateStackSet.html>`_   
 
* `delete-stack-instances <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DeleteStackInstances.html>`_   
 
* `delete-stack-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DeleteStackSet.html>`_   
 
* `describe-stack-instance <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeStackInstance.html>`_   
 
* `describe-stack-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeStackSet.html>`_   
 
* `describe-stack-set-operation <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_DescribeStackSetOperation.html>`_   
 
* `list-stack-instances <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListStackInstances.html>`_   
 
* `list-stack-set-operation-results <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListStackSetOperationResults>`_   
 
* `list-stack-set-operations <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListStackSetOperations>`_   
 
* `list-stack-sets <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_ListStackSets>`_   
 
* `stop-stack-set-operation <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StopStackSetOperation.html>`_   
 
* `update-stack-set <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_UpdateStackSet.html>`_   
 

 

Data Types

 

 
* `Parameter <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html>`_   
 
* `StackInstance <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackInstance.html.html>`_   
 
* `StackInstanceSummary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackInstanceSummary.html.html>`_   
 
* `StackSet <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSet.html>`_   
 
* `StackSetOperation <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSetOperation.html.html>`_   
 
* `StackSetOperationPreferences <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSetOperationPreferences.html.html>`_   
 
* `StackSetOperationResultSummary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSetOperationResultSummary.html.html>`_   
 
* `StackSetOperationSummary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSetOperationSummary.html.html>`_   
 
* `StackSetSummary <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_StackSetSummary.html>`_   
 
* `Tag <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Tag.html>`_   
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  cancel-update-stack
  continue-update-rollback
  create-change-set
  create-stack
  create-stack-instances
  create-stack-set
  delete-change-set
  delete-stack
  delete-stack-instances
  delete-stack-set
  deploy/index
  describe-account-limits
  describe-change-set
  describe-stack-events
  describe-stack-instance
  describe-stack-resource
  describe-stack-resources
  describe-stack-set
  describe-stack-set-operation
  describe-stacks
  estimate-template-cost
  execute-change-set
  get-stack-policy
  get-template
  get-template-summary
  list-change-sets
  list-exports
  list-imports
  list-stack-instances
  list-stack-resources
  list-stack-set-operation-results
  list-stack-set-operations
  list-stack-sets
  list-stacks
  package
  set-stack-policy
  signal-resource
  stop-stack-set-operation
  update-stack
  update-stack-set
  validate-template
  wait/index
