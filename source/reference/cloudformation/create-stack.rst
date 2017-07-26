[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation create-stack:


************
create-stack
************



===========
Description
===========



Creates a stack as specified in the template. After the call completes successfully, the stack creation starts. You can check the status of the stack via the  describe-stacks API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/CreateStack>`_


========
Synopsis
========

::

    create-stack
  --stack-name <value>
  [--template-body <value>]
  [--template-url <value>]
  [--parameters <value>]
  [--disable-rollback | --no-disable-rollback]
  [--timeout-in-minutes <value>]
  [--notification-arns <value>]
  [--capabilities <value>]
  [--resource-types <value>]
  [--role-arn <value>]
  [--on-failure <value>]
  [--stack-policy-body <value>]
  [--stack-policy-url <value>]
  [--tags <value>]
  [--client-request-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name that is associated with the stack. The name must be unique in the region in which you are creating the stack.

   

  .. note::

     

    A stack name can contain only alphanumeric characters (case sensitive) and hyphens. It must start with an alphabetic character and cannot be longer than 128 characters.

     

  

``--template-body`` (string)


  Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, go to `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify either the ``template-body`` or the ``template-url`` parameter, but not both.

  

``--template-url`` (string)


  Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information, go to the `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify either the ``template-body`` or the ``template-url`` parameter, but not both.

  

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



``--disable-rollback`` | ``--no-disable-rollback`` (boolean)


  Set to ``true`` to disable rollback of the stack if stack creation failed. You can specify either ``disable-rollback`` or ``on-failure`` , but not both.

   

  Default: ``false``  

  

``--timeout-in-minutes`` (integer)


  The amount of time that can pass before the stack status becomes CREATE_FAILED; if ``disable-rollback`` is not set or is set to ``false`` , the stack will be rolled back.

  

``--notification-arns`` (list)


  The Simple Notification Service (SNS) topic ARNs to publish stack related events. You can find your SNS topic ARNs using the SNS console or your Command Line Interface (CLI).

  



Syntax::

  "string" "string" ...



``--capabilities`` (list)


  A list of values that you must specify before AWS CloudFormation can create certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

   

  The only valid values are ``CAPABILITY_IAM`` and ``CAPABILITY_NAMED_IAM`` . The following resources require you to specify this parameter: `AWS\:\:IAM\:\:AccessKey <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-accesskey.html>`_ , `AWS\:\:IAM\:\:Group <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-group.html>`_ , `AWS\:\:IAM\:\:InstanceProfile <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-instanceprofile.html>`_ , `AWS\:\:IAM\:\:Policy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-policy.html>`_ , `AWS\:\:IAM\:\:Role <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-role.html>`_ , `AWS\:\:IAM\:\:User <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-user.html>`_ , and `AWS\:\:IAM\:\:UserToGroupAddition <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-addusertogroup.html>`_ . If your stack template contains these resources, we recommend that you review all permissions associated with them and edit their permissions if necessary.

   

  If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify ``CAPABILITY_NAMED_IAM`` . If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

   

  For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#capabilities>`_ .

  



Syntax::

  "string" "string" ...

  Where valid values are:
    CAPABILITY_IAM
    CAPABILITY_NAMED_IAM





``--resource-types`` (list)


  The template resource types that you have permissions to work with for this create stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` . Use the following syntax to describe template resource types: ``AWS::*`` (for all AWS resource), ``Custom::*`` (for all custom resources), ``Custom::*logical_ID* `` (for a specific custom resource), ``AWS::*service_name* ::*`` (for all resources of a particular AWS service), and ``AWS::*service_name* ::*resource_logical_ID* `` (for a specific AWS resource).

   

  If the list of resource types doesn't include a resource that you're creating, the stack creation fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html>`_ .

  



Syntax::

  "string" "string" ...



``--role-arn`` (string)


  The Amazon Resource Name (ARN) of an AWS Identity and Access Management (IAM) role that AWS CloudFormation assumes to create the stack. AWS CloudFormation uses the role's credentials to make calls on your behalf. AWS CloudFormation always uses this role for all future operations on the stack. As long as users have permission to operate on the stack, AWS CloudFormation uses this role even if the users don't have permission to pass it. Ensure that the role grants least privilege.

   

  If you don't specify a value, AWS CloudFormation uses the role that was previously associated with the stack. If no role is available, AWS CloudFormation uses a temporary session that is generated from your user credentials.

  

``--on-failure`` (string)


  Determines what action will be taken if stack creation fails. This must be one of: DO_NOTHING, ROLLBACK, or DELETE. You can specify either ``on-failure`` or ``disable-rollback`` , but not both.

   

  Default: ``ROLLBACK``  

  

  Possible values:

  
  *   ``DO_NOTHING``

  
  *   ``ROLLBACK``

  
  *   ``DELETE``

  

  

``--stack-policy-body`` (string)


  Structure containing the stack policy body. For more information, go to `Prevent Updates to Stack Resources <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html>`_ in the *AWS CloudFormation User Guide* . You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--stack-policy-url`` (string)


  Location of a file containing the stack policy. The URL must point to a policy (maximum size: 16 KB) located in an S3 bucket in the same region as the stack. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--tags`` (list)


  Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to the resources created in the stack. A maximum number of 50 tags can be specified.

  



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


  A unique identifier for this ``create-stack`` request. Specify this token if you plan to retry requests so that AWS CloudFormation knows that you're not attempting to create a stack with the same name. You might retry ``create-stack`` requests to ensure that AWS CloudFormation successfully received them.

   

  All events triggered by a given stack operation are assigned the same client request token, which you can use to track operations. For example, if you execute a ``create-stack`` operation with the token ``token1`` , then all the ``StackEvents`` generated by that operation will have ``client-request-token`` set as ``token1`` .

   

  In the console, stack operations display the client request token on the Events tab. Stack operations that are initiated from the console use the token format *Console-StackOperation-ID* , which helps you easily identify the stack operation . For example, if you create a stack using the console, each stack event would be assigned the same token in the following format: ``Console-CreateStack-7f59c3cf-00d2-40c7-b2ff-e75db0987002`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an AWS CloudFormation stack**

The following ``create-stacks`` command creates a stack with the name ``myteststack`` using the ``sampletemplate.json`` template::

  aws cloudformation create-stack --stack-name myteststack --template-body file://sampletemplate.json --parameters ParameterKey=KeyPairName,ParameterValue=TestKey ParameterKey=SubnetIDs,ParameterValue=SubnetID1\\,SubnetID2

Output::

  {
      "StackId": "arn:aws:cloudformation:us-east-1:123456789012:stack/myteststack/466df9e0-0dff-08e3-8e2f-5088487c4896"
  }

For more information, see `Stacks`_ in the *AWS CloudFormation User Guide*.

.. _`Stacks`: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/concept-stack.html


======
Output
======

StackId -> (string)

  

  Unique identifier of the stack.

  

  

