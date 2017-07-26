[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation get-template:


************
get-template
************



===========
Description
===========



Returns the template body for a specified stack. You can get the template for running or deleted stacks.

 

For deleted stacks, get-template returns the template for up to 90 days after the stack has been deleted.

 

.. note::

  If the template does not exist, a ``ValidationError`` is returned. 



========
Synopsis
========

::

    get-template
  --stack-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

   

   
  * Running stacks: You can specify either the stack's name or its unique stack ID.
   
  * Deleted stacks: You must specify the unique stack ID.
   

   

  Default: There is no default value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view the template body for an AWS CloudFormation stack**

The following ``get-template`` command shows the template for the ``myteststack`` stack::

  aws cloudformation get-template --stack-name myteststack

Output::

  {
      "TemplateBody": {
          "AWSTemplateFormatVersion": "2010-09-09",
          "Outputs": {
              "BucketName": {
                  "Description": "Name of S3 bucket to hold website content",
                  "Value": {
                      "Ref": "S3Bucket"
                  }
              }
          },
          "Description": "AWS CloudFormation Sample Template S3_Bucket: Sample template showing how to create a publicly accessible S3 bucket. **WARNING** This template creates an S3 bucket. You will be billed for the AWS resources used if you create a stack from this template.",
          "Resources": {
              "S3Bucket": {
                  "Type": "AWS::S3::Bucket",
                  "Properties": {
                      "AccessControl": "PublicRead"
                  }
              }
          }
      }
  }

======
Output
======

TemplateBody -> (string)

  

  Structure containing the template body. (For more information, go to `Template Anatomy`_ in the AWS CloudFormation User Guide.)

  

  



.. _Template Anatomy: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html
