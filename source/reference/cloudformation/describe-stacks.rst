[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-stacks:


***************
describe-stacks
***************



===========
Description
===========



Returns the description for the specified stack; if no stack name was specified, then it returns the description for all the stacks created.

 

.. note::

   

  If the stack does not exist, an ``AmazonCloudFormationException`` is returned.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeStacks>`_


``describe-stacks`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Stacks``


========
Synopsis
========

::

    describe-stacks
  [--stack-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




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

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe AWS CloudFormation stacks**

The following ``describe-stacks`` command shows summary information for the ``myteststack`` stack::

  aws cloudformation describe-stacks --stack-name myteststack

Output::

  {
      "Stacks":  [
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

Stacks -> (list)

  

  A list of stack structures.

  

  (structure)

    

    The Stack data type.

    

    StackId -> (string)

      

      Unique identifier of the stack.

      

      

    StackName -> (string)

      

      The name associated with the stack.

      

      

    ChangeSetId -> (string)

      

      The unique ID of the change set.

      

      

    Description -> (string)

      

      A user-defined description associated with the stack.

      

      

    Parameters -> (list)

      

      A list of ``Parameter`` structures.

      

      (structure)

        

        The Parameter data type.

        

        ParameterKey -> (string)

          

          The key associated with the parameter. If you don't specify a key and value for a particular parameter, AWS CloudFormation uses the default value that is specified in your template.

          

          

        ParameterValue -> (string)

          

          The value associated with the parameter.

          

          

        UsePreviousValue -> (boolean)

          

          During a stack update, use the existing parameter value that the stack is using for a given parameter key. If you specify ``true`` , do not specify a parameter value.

          

          

        

      

    CreationTime -> (timestamp)

      

      The time at which the stack was created.

      

      

    LastUpdatedTime -> (timestamp)

      

      The time the stack was last updated. This field will only be returned if the stack has been updated at least once.

      

      

    StackStatus -> (string)

      

      Current status of the stack.

      

      

    StackStatusReason -> (string)

      

      Success/failure message associated with the stack status.

      

      

    DisableRollback -> (boolean)

      

      Boolean to enable or disable rollback on stack creation failures:

       

       
      * ``true`` : disable rollback 
       
      * ``false`` : enable rollback 
       

      

      

    NotificationARNs -> (list)

      

      SNS topic ARNs to which stack related events are published.

      

      (string)

        

        

      

    TimeoutInMinutes -> (integer)

      

      The amount of time within which stack creation should complete.

      

      

    Capabilities -> (list)

      

      The capabilities allowed in the stack.

      

      (string)

        

        

      

    Outputs -> (list)

      

      A list of output structures.

      

      (structure)

        

        The Output data type.

        

        OutputKey -> (string)

          

          The key associated with the output.

          

          

        OutputValue -> (string)

          

          The value associated with the output.

          

          

        Description -> (string)

          

          User defined description associated with the output.

          

          

        ExportName -> (string)

          

          The name of the export associated with the output.

          

          

        

      

    RoleARN -> (string)

      

      The Amazon Resource Name (ARN) of an AWS Identity and Access Management (IAM) role that is associated with the stack. During a stack operation, AWS CloudFormation uses this role's credentials to make calls on your behalf.

      

      

    Tags -> (list)

      

      A list of ``Tag`` s that specify information about the stack.

      

      (structure)

        

        The Tag type enables you to specify a key-value pair that can be used to store information about an AWS CloudFormation stack.

        

        Key -> (string)

          

           *Required* . A string used to identify this tag. You can specify a maximum of 128 characters for a tag key. Tags owned by Amazon Web Services (AWS) have the reserved prefix: ``aws:`` .

          

          

        Value -> (string)

          

           *Required* . A string containing the value for this tag. You can specify a maximum of 256 characters for a tag value.

          

          

        

      

    

  

NextToken -> (string)

  

  If the output exceeds 1 MB in size, a string that identifies the next page of stacks. If no additional page exists, this value is null.

  

  

