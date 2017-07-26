[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation validate-template:


*****************
validate-template
*****************



===========
Description
===========



Validates a specified template. AWS CloudFormation first checks if the template is valid JSON. If it isn't, AWS CloudFormation checks if the template is valid YAML. If both these checks fail, AWS CloudFormation returns a template validation error.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ValidateTemplate>`_


========
Synopsis
========

::

    validate-template
  [--template-body <value>]
  [--template-url <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--template-body`` (string)


  Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information, go to `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must pass ``template-url`` or ``template-body`` . If both are passed, only ``template-body`` is used.

  

``--template-url`` (string)


  Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must pass ``template-url`` or ``template-body`` . If both are passed, only ``template-body`` is used.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To validate an AWS CloudFormation template**

The following ``validate-template`` command validates the ``sampletemplate.json`` template::

  aws cloudformation validate-template --template-body file://sampletemplate.json

Output::

  {
      "Description": "AWS CloudFormation Sample Template S3_Bucket: Sample template showing how to create a publicly accessible S3 bucket. **WARNING** This template creates an S3 bucket. You will be billed for the AWS resources used if you create a stack from this template.",
      "Parameters": [],
      "Capabilities": []
  }

For more information, see `Working with AWS CloudFormation Templates`_ in the *AWS CloudFormation User Guide*.

.. _`Working with AWS CloudFormation Templates`: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-guide.html


======
Output
======

Parameters -> (list)

  

  A list of ``TemplateParameter`` structures.

  

  (structure)

    

    The TemplateParameter data type.

    

    ParameterKey -> (string)

      

      The name associated with the parameter.

      

      

    DefaultValue -> (string)

      

      The default value associated with the parameter.

      

      

    NoEcho -> (boolean)

      

      Flag indicating whether the parameter should be displayed as plain text in logs and UIs.

      

      

    Description -> (string)

      

      User defined description associated with the parameter.

      

      

    

  

Description -> (string)

  

  The description found within the template.

  

  

Capabilities -> (list)

  

  The capabilities found within the template. If your template contains IAM resources, you must specify the CAPABILITY_IAM or CAPABILITY_NAMED_IAM value for this parameter when you use the  create-stack or  update-stack actions with your template; otherwise, those actions return an InsufficientCapabilities error.

   

  For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#capabilities>`_ .

  

  (string)

    

    

  

CapabilitiesReason -> (string)

  

  The list of resources that generated the values in the ``Capabilities`` response element.

  

  

DeclaredTransforms -> (list)

  

  A list of the transforms that are declared in the template.

  

  (string)

    

    

  

