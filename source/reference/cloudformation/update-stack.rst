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

 

For more information about creating an update template, updating a stack, and monitoring the progress of the update, see `Updating a Stack`_ .



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
  [--stack-policy-body <value>]
  [--stack-policy-url <value>]
  [--notification-arns <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or unique stack ID of the stack to update.

  

``--template-body`` (string)


  Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. (For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.)

   

  Conditional: You must specify either the ``template-body`` or the ``template-url`` parameter, but not both.

  

``--template-url`` (string)


  Location of file containing the template body. The URL must point to a template that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify either the ``template-body`` or the ``template-url`` parameter, but not both.

  

``--use-previous-template`` | ``--no-use-previous-template`` (boolean)


  Reuse the existing template that is associated with the stack that you are updating.

  

``--stack-policy-during-update-body`` (string)


  Structure containing the temporary overriding stack policy body. You can specify either the ``stack-policy-during-update-body`` or the ``stack-policy-during-update-url`` parameter, but not both.

   

  If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

  

``--stack-policy-during-update-url`` (string)


  Location of a file containing the temporary overriding stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``stack-policy-during-update-body`` or the ``stack-policy-during-update-url`` parameter, but not both.

   

  If you want to update protected resources, specify a temporary overriding stack policy during this update. If you do not specify a stack policy, the current policy that is associated with the stack will be used.

  

``--parameters`` (list)


  A list of ``Parameter`` structures that specify input parameters for the stack. For more information, see the `Parameter`_ data type.

  



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


  A list of capabilities that you must specify before AWS CloudFormation can create or update certain stacks. Some stack templates might include resources that can affect permissions in your AWS account. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter. Currently, the only valid value is ``CAPABILITY_IAM`` , which is required for the following resources: `AWS\:\:IAM\:\:AccessKey`_ , `AWS\:\:IAM\:\:Group`_ , `AWS\:\:IAM\:\:InstanceProfile`_ , `AWS\:\:IAM\:\:Policy`_ , `AWS\:\:IAM\:\:Role`_ , `AWS\:\:IAM\:\:User`_ , and `AWS\:\:IAM\:\:UserToGroupAddition`_ . If your stack template contains these resources, we recommend that you review any permissions associated with them. If you don't specify this parameter, this action returns an InsufficientCapabilities error.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    CAPABILITY_IAM





``--resource-types`` (list)


  The template resource types that you have permissions to work with for this update stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` .

   

  If the list of resource types doesn't include a resource that you're updating, the stack update fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management`_ .

  



Syntax::

  "string" "string" ...



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


  Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to supported resources in the stack. You can specify a maximum number of 10 tags.

   

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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  



.. _AWS\:\:IAM\:\:Group: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-group.html
.. _Updating a Stack: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks.html
.. _AWS\:\:IAM\:\:Role: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-role.html
.. _AWS\:\:IAM\:\:Policy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-policy.html
.. _Controlling Access with AWS Identity and Access Management: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html
.. _AWS\:\:IAM\:\:InstanceProfile: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-instanceprofile.html
.. _AWS\:\:IAM\:\:UserToGroupAddition: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-addusertogroup.html
.. _Template Anatomy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html
.. _AWS\:\:IAM\:\:User: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-user.html
.. _AWS\:\:IAM\:\:AccessKey: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-accesskey.html
.. _Parameter: http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html
