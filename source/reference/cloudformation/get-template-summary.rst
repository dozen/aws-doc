[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation get-template-summary:


********************
get-template-summary
********************



===========
Description
===========



Returns information about a new or existing template. The ``get-template-summary`` action is useful for viewing parameter information, such as default parameter values and parameter types, before you create or update a stack.

 

You can use the ``get-template-summary`` action when you submit a template, or you can get template information for a running or deleted stack.

 

For deleted stacks, ``get-template-summary`` returns the template information for up to 90 days after the stack has been deleted. If the template does not exist, a ``ValidationError`` is returned.



========
Synopsis
========

::

    get-template-summary
  [--template-body <value>]
  [--template-url <value>]
  [--stack-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--template-body`` (string)


  Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. For more information about templates, see `Template Anatomy`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify only one of the following parameters: ``StackName`` , ``template-body`` , or ``template-url`` .

  

``--template-url`` (string)


  Location of file containing the template body. The URL must point to a template (max size: 460,800 bytes) that is located in an Amazon S3 bucket. For more information about templates, see `Template Anatomy`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must specify only one of the following parameters: ``StackName`` , ``template-body`` , or ``template-url`` .

  

``--stack-name`` (string)


  The name or the stack ID that is associated with the stack, which are not always interchangeable. For running stacks, you can specify either the stack's name or its unique stack ID. For deleted stack, you must specify the unique stack ID.

   

  Conditional: You must specify only one of the following parameters: ``StackName`` , ``template-body`` , or ``template-url`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Parameters -> (list)

  

  A list of parameter declarations that describe various properties for each parameter.

  

  (structure)

    

    The ParameterDeclaration data type.

    

    ParameterKey -> (string)

      

      The name that is associated with the parameter.

      

      

    DefaultValue -> (string)

      

      The default value of the parameter.

      

      

    ParameterType -> (string)

      

      The type of parameter.

      

      

    NoEcho -> (boolean)

      

      Flag that indicates whether the parameter value is shown as plain text in logs and in the AWS Management Console.

      

      

    Description -> (string)

      

      The description that is associate with the parameter.

      

      

    ParameterConstraints -> (structure)

      

      The criteria that AWS CloudFormation uses to validate parameter values.

      

      AllowedValues -> (list)

        

        A list of values that are permitted for a parameter.

        

        (string)

          

          

        

      

    

  

Description -> (string)

  

  The value that is defined in the ``Description`` property of the template.

  

  

Capabilities -> (list)

  

  The capabilities found within the template. Currently, AWS CloudFormation supports only the CAPABILITY_IAM capability. If your template contains IAM resources, you must specify the CAPABILITY_IAM value for this parameter when you use the  create-stack or  update-stack actions with your template; otherwise, those actions return an InsufficientCapabilities error.

  

  (string)

    

    

  

CapabilitiesReason -> (string)

  

  The list of resources that generated the values in the ``Capabilities`` response element.

  

  

ResourceTypes -> (list)

  

  A list of all the template resource types that are defined in the template, such as ``AWS::EC2::Instance`` , ``AWS::Dynamo::Table`` , and ``Custom::MyCustomInstance`` .

  

  (string)

    

    

  

Version -> (string)

  

  The AWS template format version, which identifies the capabilities of the template.

  

  

Metadata -> (string)

  

  The value that is defined for the ``Metadata`` property of the template.

  

  



.. _Template Anatomy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html
