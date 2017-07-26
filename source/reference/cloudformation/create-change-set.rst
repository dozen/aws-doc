[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation create-change-set:


*****************
create-change-set
*****************



===========
Description
===========



Creates a list of changes that will be applied to a stack so that you can review the changes before executing them. You can create a change set for a stack that doesn't exist or an existing stack. If you create a change set for a stack that doesn't exist, the change set shows all of the resources that AWS CloudFormation will create. If you create a change set for an existing stack, AWS CloudFormation compares the stack's information with the information that you submit in the change set and lists the differences. Use change sets to understand which resources AWS CloudFormation will create or change, and how it will change resources in an existing stack, before you create or update a stack.

 

To create a change set for a stack that doesn't exist, for the ``change-set-type`` parameter, specify ``CREATE`` . To create a change set for an existing stack, specify ``UPDATE`` for the ``change-set-type`` parameter. After the ``create-change-set`` call successfully completes, AWS CloudFormation starts creating the change set. To check the status of the change set or to review it, use the  describe-change-set action.

 

When you are satisfied with the changes the change set will make, execute the change set by using the  execute-change-set action. AWS CloudFormation doesn't make changes until you execute the change set.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/CreateChangeSet>`_


========
Synopsis
========

::

    create-change-set
  --stack-name <value>
  [--template-body <value>]
  [--template-url <value>]
  [--use-previous-template | --no-use-previous-template]
  [--parameters <value>]
  [--capabilities <value>]
  [--resource-types <value>]
  [--role-arn <value>]
  [--notification-arns <value>]
  [--tags <value>]
  --change-set-name <value>
  [--client-token <value>]
  [--description <value>]
  [--change-set-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique ID of the stack for which you are creating a change set. AWS CloudFormation generates the change set by comparing this stack's information with the information that you submit, such as a modified template or different parameter input values.

  

``--template-body`` (string)


  A structure that contains the body of the revised template, with a minimum length of 1 byte and a maximum length of 51,200 bytes. AWS CloudFormation generates the change set by comparing this template with the template of the stack that you specified.

   

  Conditional: You must specify only ``template-body`` or ``template-url`` .

  

``--template-url`` (string)


  The location of the file that contains the revised template. The URL must point to a template (max size: 460,800 bytes) that is located in an S3 bucket. AWS CloudFormation generates the change set by comparing this template with the stack that you specified.

   

  Conditional: You must specify only ``template-body`` or ``template-url`` .

  

``--use-previous-template`` | ``--no-use-previous-template`` (boolean)


  Whether to reuse the template that is associated with the stack to create the change set.

  

``--parameters`` (list)


  A list of ``Parameter`` structures that specify input parameters for the change set. For more information, see the `Parameter <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html>`_ data type.

  



Shorthand Syntax::

    ParameterKey=string,ParameterValue=string,UsePreviousValue=boolean ...




JSON Syntax::

  [
    {
      "ParameterKey": "string",
      "ParameterValue": "string",
      "UsePreviousValue": true|false
    }
    ...
  ]



``--capabilities`` (list)


  A list of values that you must specify before AWS CloudFormation can update certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

   

  The only valid values are ``CAPABILITY_IAM`` and ``CAPABILITY_NAMED_IAM`` . The following resources require you to specify this parameter: `AWS\:\:IAM\:\:AccessKey <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-accesskey.html>`_ , `AWS\:\:IAM\:\:Group <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-group.html>`_ , `AWS\:\:IAM\:\:InstanceProfile <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-instanceprofile.html>`_ , `AWS\:\:IAM\:\:Policy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-policy.html>`_ , `AWS\:\:IAM\:\:Role <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-role.html>`_ , `AWS\:\:IAM\:\:User <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-user.html>`_ , and `AWS\:\:IAM\:\:UserToGroupAddition <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-addusertogroup.html>`_ . If your stack template contains these resources, we recommend that you review all permissions associated with them and edit their permissions if necessary.

   

  If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify ``CAPABILITY_NAMED_IAM`` . If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

   

  For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#capabilities>`_ .

  



Syntax::

  "string" "string" ...

  Where valid values are:
    CAPABILITY_IAM
    CAPABILITY_NAMED_IAM





``--resource-types`` (list)


  The template resource types that you have permissions to work with if you execute this change set, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` .

   

  If the list of resource types doesn't include a resource type that you're updating, the stack update fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for condition keys in IAM policies for AWS CloudFormation. For more information, see `Controlling Access with AWS Identity and Access Management <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html>`_ in the AWS CloudFormation User Guide.

  



Syntax::

  "string" "string" ...



``--role-arn`` (string)


  The Amazon Resource Name (ARN) of an AWS Identity and Access Management (IAM) role that AWS CloudFormation assumes when executing the change set. AWS CloudFormation uses the role's credentials to make calls on your behalf. AWS CloudFormation uses this role for all future operations on the stack. As long as users have permission to operate on the stack, AWS CloudFormation uses this role even if the users don't have permission to pass it. Ensure that the role grants least privilege.

   

  If you don't specify a value, AWS CloudFormation uses the role that was previously associated with the stack. If no role is available, AWS CloudFormation uses a temporary session that is generated from your user credentials.

  

``--notification-arns`` (list)


  The Amazon Resource Names (ARNs) of Amazon Simple Notification Service (Amazon SNS) topics that AWS CloudFormation associates with the stack. To remove all associated notification topics, specify an empty list.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to resources in the stack. You can specify a maximum of 50 tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--change-set-name`` (string)


  The name of the change set. The name must be unique among all change sets that are associated with the specified stack.

   

  A change set name can contain only alphanumeric, case sensitive characters and hyphens. It must start with an alphabetic character and cannot exceed 128 characters.

  

``--client-token`` (string)


  A unique identifier for this ``create-change-set`` request. Specify this token if you plan to retry requests so that AWS CloudFormation knows that you're not attempting to create another change set with the same name. You might retry ``create-change-set`` requests to ensure that AWS CloudFormation successfully received them.

  

``--description`` (string)


  A description to help you identify this change set.

  

``--change-set-type`` (string)


  The type of change set operation. To create a change set for a new stack, specify ``CREATE`` . To create a change set for an existing stack, specify ``UPDATE`` .

   

  If you create a change set for a new stack, AWS Cloudformation creates a stack with a unique stack ID, but no template or resources. The stack will be in the ` ``REVIEW_IN_PROGRESS`` http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-describing-stacks.html#d0e11995`_ state until you execute the change set.

   

  By default, AWS CloudFormation specifies ``UPDATE`` . You can't use the ``UPDATE`` type to create a change set for a new stack or the ``CREATE`` type to create a change set for an existing stack.

  

  Possible values:

  
  *   ``CREATE``

  
  *   ``UPDATE``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Id -> (string)

  

  The Amazon Resource Name (ARN) of the change set.

  

  

StackId -> (string)

  

  The unique ID of the stack.

  

  



.. _http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-describing-stacks.html#d0e11995: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-describing-stacks.html#d0e11995
