[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation create-stack:


************
create-stack
************



===========
Description
===========



Creates a stack as specified in the template. After the call completes successfully, the stack creation starts. You can check the status of the stack via the  describe-stacks API.



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
  [--on-failure <value>]
  [--stack-policy-body <value>]
  [--stack-policy-url <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name that is associated with the stack. The name must be unique in the region in which you are creating the stack.

   

  .. note::

    A stack name can contain only alphanumeric characters (case sensitive) and hyphens. It must start with an alphabetic character and cannot be longer than 128 characters.

  

``--template-body`` (string)


  Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify either the ``template-body`` or the ``template-url`` parameter, but not both.

  

``--template-url`` (string)


  Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information, go to the `Template Anatomy`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify either the ``template-body`` or the ``template-url`` parameter, but not both.

  

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



``--disable-rollback`` | ``--no-disable-rollback`` (boolean)


  Set to ``true`` to disable rollback of the stack if stack creation failed. You can specify either ``no-disable-rollback`` or ``on-failure`` , but not both.

   

  Default: ``false``  

  

``--timeout-in-minutes`` (integer)


  The amount of time that can pass before the stack status becomes CREATE_FAILED; if ``no-disable-rollback`` is not set or is set to ``false`` , the stack will be rolled back.

  

``--notification-arns`` (list)


  The Simple Notification Service (SNS) topic ARNs to publish stack related events. You can find your SNS topic ARNs using the `SNS console`_ or your Command Line Interface (CLI).

  



Syntax::

  "string" "string" ...



``--capabilities`` (list)


  A list of capabilities that you must specify before AWS CloudFormation can create or update certain stacks. Some stack templates might include resources that can affect permissions in your AWS account. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter.

   

  Currently, the only valid value is ``CAPABILITY_IAM`` , which is required for the following resources: `AWS\:\:IAM\:\:AccessKey`_ , `AWS\:\:IAM\:\:Group`_ , `AWS\:\:IAM\:\:InstanceProfile`_ , `AWS\:\:IAM\:\:Policy`_ , `AWS\:\:IAM\:\:Role`_ , `AWS\:\:IAM\:\:User`_ , and `AWS\:\:IAM\:\:UserToGroupAddition`_ . If your stack template contains these resources, we recommend that you review any permissions associated with them. If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    CAPABILITY_IAM





``--resource-types`` (list)


  The template resource types that you have permissions to work with for this create stack action, such as ``AWS::EC2::Instance`` , ``AWS::EC2::*`` , or ``Custom::MyCustomInstance`` . Use the following syntax to describe template resource types: ``AWS::*`` (for all AWS resource), ``Custom::*`` (for all custom resources), ``Custom::*logical_ID*`` (for a specific custom resource), ``AWS::*service_name* ::*`` (for all resources of a particular AWS service), and ``AWS::*service_name* ::*resource_logical_ID*`` (for a specific AWS resource).

   

  If the list of resource types doesn't include a resource that you're creating, the stack creation fails. By default, AWS CloudFormation grants permissions to all resource types. AWS Identity and Access Management (IAM) uses this parameter for AWS CloudFormation-specific condition keys in IAM policies. For more information, see `Controlling Access with AWS Identity and Access Management`_ .

  



Syntax::

  "string" "string" ...



``--on-failure`` (string)


  Determines what action will be taken if stack creation fails. This must be one of: DO_NOTHING, ROLLBACK, or DELETE. You can specify either ``on-failure`` or ``no-disable-rollback`` , but not both.

   

  Default: ``ROLLBACK`` 

  

  Possible values:

  
  *   ``DO_NOTHING``

  
  *   ``ROLLBACK``

  
  *   ``DELETE``

  

  

``--stack-policy-body`` (string)


  Structure containing the stack policy body. For more information, go to `Prevent Updates to Stack Resources`_ in the AWS CloudFormation User Guide. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--stack-policy-url`` (string)


  Location of a file containing the stack policy. The URL must point to a policy (max size: 16KB) located in an S3 bucket in the same region as the stack. You can specify either the ``stack-policy-body`` or the ``stack-policy-url`` parameter, but not both.

  

``--tags`` (list)


  Key-value pairs to associate with this stack. AWS CloudFormation also propagates these tags to the resources created in the stack. A maximum number of 10 tags can be specified.

  



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

**To create an AWS CloudFormation stack**

The following ``create-stacks`` command creates a stack with the name ``myteststack`` using the ``sampletemplate.json`` template::

  aws cloudformation create-stack --stack-name myteststack --template-body file:////home//local//test//sampletemplate.json

Output::

  [
      {
          "StackId": "arn:aws:cloudformation:us-east-1:123456789012:stack/myteststack/466df9e0-0dff-08e3-8e2f-5088487c4896",
          "Description": "AWS CloudFormation Sample Template S3_Bucket: Sample template showing how to create a publicly accessible S3 bucket. **WARNING** This template creates an S3 bucket. You will be billed for the AWS resources used if you create a stack from this template.",
          "Tags": [],
          "Outputs": [
              {
                  "Description": "Name of S3 bucket to hold website content",
                  "OutputKey": "BucketName",
                  "OutputValue": "myteststack-s3bucket-jssofi1zie2w"
              }
          ],
          "StackStatusReason": null,
          "CreationTime": "2013-08-23T01:02:15.422Z",
          "Capabilities": [],
          "StackName": "myteststack",
          "StackStatus": "CREATE_COMPLETE",
          "DisableRollback": false
      }
  ]

For more information, see `Stacks`_ in the *AWS CloudFormation User Guide*.

.. _`Stacks`: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/concept-stack.html


======
Output
======

StackId -> (string)

  

  Unique identifier of the stack.

  

  



.. _AWS\:\:IAM\:\:Group: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-group.html
.. _AWS\:\:IAM\:\:Role: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-role.html
.. _AWS\:\:IAM\:\:Policy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-policy.html
.. _Controlling Access with AWS Identity and Access Management: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html
.. _AWS\:\:IAM\:\:InstanceProfile: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-instanceprofile.html
.. _AWS\:\:IAM\:\:UserToGroupAddition: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-addusertogroup.html
.. _Template Anatomy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html
.. _SNS console: http://console.aws.amazon.com/sns
.. _AWS\:\:IAM\:\:User: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-user.html
.. _AWS\:\:IAM\:\:AccessKey: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-accesskey.html
.. _Parameter: http://docs.aws.amazon.com/AWSCloudFormation/latest/APIReference/API_Parameter.html
.. _Prevent Updates to Stack Resources: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html
