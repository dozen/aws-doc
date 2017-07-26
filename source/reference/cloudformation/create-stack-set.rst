[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation create-stack-set:


****************
create-stack-set
****************



===========
Description
===========



Creates a stack set.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/CreateStackSet>`_


========
Synopsis
========

::

    create-stack-set
  --stack-set-name <value>
  [--description <value>]
  [--template-body <value>]
  [--template-url <value>]
  [--parameters <value>]
  [--capabilities <value>]
  [--tags <value>]
  [--client-request-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name to associate with the stack set. The name must be unique in the region where you create your stack set.

   

  .. note::

     

    A stack name can contain only alphanumeric characters (case-sensitive) and hyphens. It must start with an alphabetic character and can't be longer than 128 characters.

     

  

``--description`` (string)


  A description of the stack set. You can use the description to identify the stack set's purpose or other important information.

  

``--template-body`` (string)


  The structure that contains the template body, with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, see `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify either the template-body or the template-url parameter, but not both.

  

``--template-url`` (string)


  The location of the file that contains the template body. The URL must point to a template (maximum size: 460,800 bytes) that's located in an Amazon S3 bucket. For more information, see `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify either the template-body or the template-url parameter, but not both.

  

``--parameters`` (list)


  The input parameters for the stack set template. 

  



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


  The key-value pairs to associate with this stack set and the stacks created from it. AWS CloudFormation also propagates these tags to supported resources that are created in the stacks. A maximum number of 50 tags can be specified.

   

  If you specify tags as part of a ``create-stack-set`` action, AWS CloudFormation checks to see if you have the required IAM permission to tag resources. If you don't, the entire ``create-stack-set`` action fails with an ``access denied`` error, and the stack set is not created.

  



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


  A unique identifier for this ``create-stack-set`` request. Specify this token if you plan to retry requests so that AWS CloudFormation knows that you're not attempting to create another stack set with the same name. You might retry ``create-stack-set`` requests to ensure that AWS CloudFormation successfully received them.

   

  If you don't specify an operation ID, the SDK generates one automatically. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StackSetId -> (string)

  

  The ID of the stack set that you're creating.

  

  

