[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation update-stack-set:


****************
update-stack-set
****************



===========
Description
===========



Updates the stack set and *all* associated stack instances.

 

Even if the stack set operation created by updating the stack set fails (completely or partially, below or above a specified failure tolerance), the stack set is updated with your changes. Subsequent  create-stack-instances calls on the specified stack set use the updated stack set.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/UpdateStackSet>`_


========
Synopsis
========

::

    update-stack-set
  --stack-set-name <value>
  [--description <value>]
  [--template-body <value>]
  [--template-url <value>]
  [--use-previous-template | --no-use-previous-template]
  [--parameters <value>]
  [--capabilities <value>]
  [--tags <value>]
  [--operation-preferences <value>]
  [--operation-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or unique ID of the stack set that you want to update.

  

``--description`` (string)


  A brief description of updates that you are making.

  

``--template-body`` (string)


  The structure that contains the template body, with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, see `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify only one of the following parameters: ``template-body`` or ``template-url`` —or set ``use-previous-template`` to true.

  

``--template-url`` (string)


  The location of the file that contains the template body. The URL must point to a template (maximum size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information, see `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify only one of the following parameters: ``template-body`` or ``template-url`` —or set ``use-previous-template`` to true. 

  

``--use-previous-template`` | ``--no-use-previous-template`` (boolean)


  Use the existing template that's associated with the stack set that you're updating.

   

  Conditional: You must specify only one of the following parameters: ``template-body`` or ``template-url`` —or set ``use-previous-template`` to true. 

  

``--parameters`` (list)


  A list of input parameters for the stack set template. 

  



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


  A list of values that you must specify before AWS CloudFormation can create certain stack sets. Some stack set templates might include resources that can affect permissions in your AWS account—for example, by creating new AWS Identity and Access Management (IAM) users. For those stack sets, you must explicitly acknowledge their capabilities by specifying this parameter.

   

  The only valid values are CAPABILITY_IAM and CAPABILITY_NAMED_IAM. The following resources require you to specify this parameter: 

   

   
  * AWS::IAM::AccessKey 
   
  * AWS::IAM::Group 
   
  * AWS::IAM::InstanceProfile 
   
  * AWS::IAM::Policy 
   
  * AWS::IAM::Role 
   
  * AWS::IAM::User 
   
  * AWS::IAM::UserToGroupAddition 
   

   

  If your stack template contains these resources, we recommend that you review all permissions that are associated with them and edit their permissions if necessary.

   

  If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify CAPABILITY_NAMED_IAM. If you don't specify this parameter, this action returns an ``InsufficientCapabilities`` error.

   

  For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates. <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#capabilities>`_  

  



Syntax::

  "string" "string" ...

  Where valid values are:
    CAPABILITY_IAM
    CAPABILITY_NAMED_IAM





``--tags`` (list)


  The key-value pairs to associate with this stack set and the stacks created from it. AWS CloudFormation also propagates these tags to supported resources that are created in the stacks. You can specify a maximum number of 50 tags.

   

  If you specify tags for this parameter, those tags replace any list of tags that are currently associated with this stack set. This means:

   

   
  * If you don't specify this parameter, AWS CloudFormation doesn't modify the stack's tags.  
   
  * If you specify *any* tags using this parameter, you must specify *all* the tags that you want associated with this stack set, even tags you've specifed before (for example, when creating the stack set or during a previous update of the stack set.). Any tags that you don't include in the updated list of tags are removed from the stack set, and therefore from the stacks and resources as well.  
   
  * If you specify an empty value, AWS CloudFormation removes all currently associated tags. 
   

   

  If you specify new tags as part of an ``update-stack-set`` action, AWS CloudFormation checks to see if you have the required IAM permission to tag resources. If you omit tags that are currently associated with the stack set from the list of tags you specify, AWS CloudFormation assumes that you want to remove those tags from the stack set, and checks to see if you have permission to untag resources. If you don't have the necessary permission(s), the entire ``update-stack-set`` action fails with an ``access denied`` error, and the stack set is not updated.

  



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



``--operation-preferences`` (structure)


  Preferences for how AWS CloudFormation performs this stack set operation.

  



Shorthand Syntax::

    RegionOrder=string,string,FailureToleranceCount=integer,FailureTolerancePercentage=integer,MaxConcurrentCount=integer,MaxConcurrentPercentage=integer




JSON Syntax::

  {
    "RegionOrder": ["string", ...],
    "FailureToleranceCount": integer,
    "FailureTolerancePercentage": integer,
    "MaxConcurrentCount": integer,
    "MaxConcurrentPercentage": integer
  }



``--operation-id`` (string)


  The unique ID for this stack set operation. 

   

  The operation ID also functions as an idempotency token, to ensure that AWS CloudFormation performs the stack set operation only once, even if you retry the request multiple times. You might retry stack set operation requests to ensure that AWS CloudFormation successfully received them.

   

  If you don't specify an operation ID, AWS CloudFormation generates one automatically.

   

  Repeating this stack set operation with a new operation ID retries all stack instances whose status is ``OUTDATED`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

OperationId -> (string)

  

  The unique ID for this stack set operation.

  

  

