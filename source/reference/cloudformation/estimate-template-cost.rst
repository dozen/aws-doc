[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation estimate-template-cost:


**********************
estimate-template-cost
**********************



===========
Description
===========



Returns the estimated monthly cost of a template. The return value is an AWS Simple Monthly Calculator URL with a query string that describes the resources required to run the template.



========
Synopsis
========

::

    estimate-template-cost
  [--template-body <value>]
  [--template-url <value>]
  [--parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--template-body`` (string)


  Structure containing the template body with a minimum length of 1 byte and a maximum length of 51,200 bytes. (For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.)

   

  Conditional: You must pass ``template-body`` or ``template-url`` . If both are passed, only ``template-body`` is used.

  

``--template-url`` (string)


  Location of file containing the template body. The URL must point to a template that is located in an Amazon S3 bucket. For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.

   

  Conditional: You must pass ``template-url`` or ``template-body`` . If both are passed, only ``template-body`` is used.

  

``--parameters`` (list)


  A list of ``Parameter`` structures that specify input parameters.

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Url -> (string)

  

  An AWS Simple Monthly Calculator URL with a query string that describes the resources required to run the template.

  

  



.. _Template Anatomy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html
