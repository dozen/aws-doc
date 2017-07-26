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

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/GetTemplate>`_


========
Synopsis
========

::

    get-template
  [--stack-name <value>]
  [--change-set-name <value>]
  [--template-stage <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack, which are not always interchangeable:

   

   
  * Running stacks: You can specify either the stack's name or its unique stack ID. 
   
  * Deleted stacks: You must specify the unique stack ID. 
   

   

  Default: There is no default value.

  

``--change-set-name`` (string)


  The name or Amazon Resource Name (ARN) of a change set for which AWS CloudFormation returns the associated template. If you specify a name, you must also specify the ``stack-name`` .

  

``--template-stage`` (string)


  For templates that include transforms, the stage of the template that AWS CloudFormation returns. To get the user-submitted template, specify ``Original`` . To get the template after AWS CloudFormation has processed all transforms, specify ``Processed`` . 

   

  If the template doesn't include transforms, ``Original`` and ``Processed`` return the same template. By default, AWS CloudFormation specifies ``Original`` . 

  

  Possible values:

  
  *   ``Original``

  
  *   ``Processed``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  Structure containing the template body. (For more information, go to `Template Anatomy <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html>`_ in the AWS CloudFormation User Guide.)

   

  AWS CloudFormation returns the same template that was used when the stack was created.

  

  

StagesAvailable -> (list)

  

  The stage of the template that you can retrieve. For stacks, the ``Original`` and ``Processed`` templates are always available. For change sets, the ``Original`` template is always available. After AWS CloudFormation finishes creating the change set, the ``Processed`` template becomes available.

  

  (string)

    

    

  

