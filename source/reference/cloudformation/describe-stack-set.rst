[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stack-set:


******************
describe-stack-set
******************



===========
Description
===========



Returns the description of the specified stack set. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeStackSet>`_


========
Synopsis
========

::

    describe-stack-set
  --stack-set-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-set-name`` (string)


  The name or unique ID of the stack set whose description you want.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StackSet -> (structure)

  

  The specified stack set.

  

  StackSetName -> (string)

    

    The name that's associated with the stack set.

    

    

  StackSetId -> (string)

    

    The ID of the stack set.

    

    

  Description -> (string)

    

    A description of the stack set that you specify when the stack set is created or updated.

    

    

  Status -> (string)

    

    The status of the stack set.

    

    

  TemplateBody -> (string)

    

    The structure that contains the body of the template that was used to create or update the stack set.

    

    

  Parameters -> (list)

    

    A list of input parameters for a stack set.

    

    (structure)

      

      The Parameter data type.

      

      ParameterKey -> (string)

        

        The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

        

        

      ParameterValue -> (string)

        

        The value associated with the parameter.

        

        

      UsePreviousValue -> (boolean)

        

        During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

        

        

      

    

  Capabilities -> (list)

    

    The capabilities that are allowed in the stack set. Some stack set templates might include resources that can affect permissions in your AWS account—for example, by creating new AWS Identity and Access Management (IAM) users. For more information, see `Acknowledging IAM Resources in AWS CloudFormation Templates. <http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-iam-template.html#capabilities>`_  

    

    (string)

      

      

    

  Tags -> (list)

    

    A list of tags that specify information about the stack set. A maximum number of 50 tags can be specified.

    

    (structure)

      

      The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

      

      Key -> (string)

        

         *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

        

        

      Value -> (string)

        

         *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

        

        

      

    

  

