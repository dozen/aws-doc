[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation update-stack:


************
update-stack
************



===========
Description
===========



Updates a stack as specified in the template. After the call completes successfully, the stack update starts. You can check the status of the stack via the  describe-stacks action.

 

To get a copy of the template for an existing stack, you can use the  get-template action.

 

For more information about creating an update template, updating a stack, and monitoring the progress of the update, see `Updating a Stack <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/UpdateStack>`_


========
Synopsis
========

::

    update-stack
  --stack-name <value>
  [--template-body <value>]
  [--template-url <value>]
  [--use-previous-template | --no-use-previous-template]
  [--stack-policy-during-update-body <value>]
  [--stack-policy-during-update-url <value>]
  [--parameters <value>]
  [--capabilities <value>]
  [--resource-types <value>]
  [--role-arn <value>]
  [--stack-policy-body <value>]
  [--stack-policy-url <value>]
  [--notification-arns <value>]
  [--tags <value>]
  [--client-request-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or unique stack ID of the stack to update.

  

``--template-body`` (string)


  Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. (For more information, go to `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.)

   

  Conditional: You must specify only one of the following parameters: ``template-body`` , ``template-url`` , or set the ``use-previous-template`` to ``true`` .

  

``--template-url`` (string)


  Location of file containing the template body. The URL must point to a template that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify only one of the following parameters: ``template-body`` , ``template-url`` , or set the ``use-previous-template`` to ``true`` .

  

``--use-previous-template`` | ``--no-use-previous-template`` (boolean)


  Reuse the existing template that is associated with the stack that you are updating.

   

  Conditional: You must specify only one of the following parameters: ``template-body`` , ``template-url`` , or set the ``use-previous-template`` to ``true`` .

  

``--stack-policy-during-update-body`` (string)


  Structure containing the temporary overriding stack policy body. You can specify either the ``stack-policy-during-update-body`` or the ``stack-policy-during-update-url`` parameter, but not both.

   

  If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

  

``--stack-policy-during-update-url`` (string)


  Location of a file containing the temporary overriding stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``stack-policy-during-update-body`` or the ``stack-policy-during-update-url`` parameter, but not both.

   

  If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

  

``--parameters`` (list)


  A list of ``Parameter`` structures that specify input parameters for the stack. For more information, see the `Parameter <http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html>`_ data type.

  



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


  The template resource types that you have permissions to work with for this update stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` .

   

  If the list of resource types doesn't include a resource that you're updating, the stack update fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html>`_ .

  



Syntax::

  "string" "string" ...



``--role-arn`` (string)


  The Amazon Resource Name (ARN) of an AWS Identity and Access Management (IAM) role that AWS CloudFormation assumes to update the stack. AWS CloudFormation uses the role's credentials to make calls on your behalf. AWS CloudFormation always uses this role for all future operations on the stack. As long as users have permission to operate on the stack, AWS CloudFormation uses this role even if the users don't have permission to pass it. Ensure that the role grants least privilege.

   

  If you don't specify a value, AWS CloudFormation uses the role that was previously associated with the stack. If no role is available, AWS CloudFormation uses a temporary session that is generated from your user credentials.

  

``--stack-policy-body`` (string)


  Structure containing a new stack policy body. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

   

  You might update the stack policy, for example, in order to protect a new resource that you created during a stack update. If you do not specify a stack policy, the current policy that is associated with the stack is unchanged.

  

``--stack-policy-url`` (string)


  Location of a file containing the updated stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

   

  You might update the stack policy, for example, in order to protect a new resource that you created during a stack update. If you do not specify a stack policy, the current policy that is associated with the stack is unchanged.

  

``--notification-arns`` (list)


  Amazon Simple Notification Service topic Amazon Resource Names (ARNs) that AWS CloudFormation associates with the stack. Specify an empty list to remove all notification topics.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to supported resources in the stack. You can specify a maximum number of 50 tags.

   

  If you don't specify this parameter, AWS CloudFormation doesn't modify the stack's tags. If you specify an empty value, AWS CloudFormation removes all associated tags.

  



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



``--client-request-token`` (string)


  A unique identifier for this ``update-stack`` request. Specify this token if you plan to retry requests so that AWS CloudFormation knows that you're not attempting to update a stack with the same name. You might retry ``update-stack`` requests to ensure that AWS CloudFormation successfully received them.

   

  All events triggered by a given stack operation are assigned the same client request token, which you can use to track operations. For example, if you execute a ``create-stack`` operation with the token ``token1`` , then all the ``StackEvents`` generated by that operation will have ``client-request-token`` set as ``token1`` .

   

  In the console, stack operations display the client request token on the Events tab. Stack operations that are initiated from the console use the token format *Console-StackOperation-ID* , which helps you easily identify the stack operation . For example, if you create a stack using the console, each stack event would be assigned the same token in the following format: ``Console-CreateStack-7f59c3cf-00d2-40c7-b2ff-e75db0987002`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update AWS CloudFormation stacks**

The following ``update-stack`` command updates the template and input parameters for the ``mystack`` stack::

  aws cloudformation update-stack --stack-name mystack --template-url https://s3.amazonaws.com/sample/updated.template --parameters ParameterKey=KeyPairName,ParameterValue=SampleKeyPair ParameterKey=SubnetIDs,ParameterValue=SampleSubnetID1\\,SampleSubnetID2

The following ``update-stack`` command updates just the ``SubnetIDs`` parameter value for the ``mystack`` stack. If you
don't specify a parameter value, the default value that is specified in the template is used::

  aws cloudformation update-stack --stack-name mystack --template-url https://s3.amazonaws.com/sample/updated.template --parameters ParameterKey=KeyPairName,UsePreviousValue=true ParameterKey=SubnetIDs,ParameterValue=SampleSubnetID1\\,UpdatedSampleSubnetID2

The following ``update-stack`` command adds two stack notification topics to the ``mystack`` stack::

  aws cloudformation update-stack --stack-name mystack --use-previous-template --notification-arns "arn:aws:sns:use-east-1:123456789012:mytopic1" "arn:aws:sns:us-east-1:123456789012:mytopic2"

For more information, see `Updating a Stack`_ in the *AWS CloudFormation User Guide*.


======
Output
======

StackId -> (string)

  

  Unique identifier of the stack.

  

  

