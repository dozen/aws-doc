[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation list-stacks:


***********
list-stacks
***********



===========
Description
===========



Returns the summary information for stacks whose status matches the specified StackStatusFilter. Summary information for stacks that have been deleted is kept for 90 days after the stack is deleted. If no stack-status-filter is specified, summary information for all stacks is returned (including existing stacks and stacks that have been deleted).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ListStacks>`_


``list-stacks`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``StackSummaries``


========
Synopsis
========

::

    list-stacks
  [--stack-status-filter <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-status-filter`` (list)


  Stack status to use as a filter. Specify one or more stack status codes to list only stacks with the specified status codes. For a complete list of stack status codes, see the ``StackStatus`` parameter of the  Stack data type.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    CREATE_IN_PROGRESS
    CREATE_FAILED
    CREATE_COMPLETE
    ROLLBACK_IN_PROGRESS
    ROLLBACK_FAILED
    ROLLBACK_COMPLETE
    DELETE_IN_PROGRESS
    DELETE_FAILED
    DELETE_COMPLETE
    UPDATE_IN_PROGRESS
    UPDATE_COMPLETE_CLEANUP_IN_PROGRESS
    UPDATE_COMPLETE
    UPDATE_ROLLBACK_IN_PROGRESS
    UPDATE_ROLLBACK_FAILED
    UPDATE_ROLLBACK_COMPLETE_CLEANUP_IN_PROGRESS
    UPDATE_ROLLBACK_COMPLETE
    REVIEW_IN_PROGRESS





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

**To list AWS CloudFormation stacks**

The following ``list-stacks`` command shows a summary of all stacks that have a status of ``CREATE_COMPLETE``::

  aws cloudformation list-stacks --stack-status-filter CREATE_COMPLETE

Output::

  [
      {
          "StackId": "arn:aws:cloudformation:us-east-1:123456789012:stack/myteststack/466df9e0-0dff-08e3-8e2f-5088487c4896",
          "TemplateDescription": "AWS CloudFormation Sample Template S3_Bucket: Sample template showing how to create a publicly accessible S3 bucket. **WARNING** This template creates an S3 bucket. You will be billed for the AWS resources used if you create a stack from this template.",
          "StackStatusReason": null,
          "CreationTime": "2013-08-26T03:27:10.190Z",
          "StackName": "myteststack",
          "StackStatus": "CREATE_COMPLETE"
      }
  ]

======
Output
======

StackSummaries -> (list)

  

  A list of ``StackSummary`` structures containing information about the specified stacks.

  

  (structure)

    

    The StackSummary Data Type

    

    StackId -> (string)

      

      Unique stack identifier.

      

      

    StackName -> (string)

      

      The name associated with the stack.

      

      

    TemplateDescription -> (string)

      

      The template description of the template used to create the stack.

      

      

    CreationTime -> (timestamp)

      

      The time the stack was created.

      

      

    LastUpdatedTime -> (timestamp)

      

      The time the stack was last updated. This field will only be returned if the stack has been updated at least once.

      

      

    DeletionTime -> (timestamp)

      

      The time the stack was deleted.

      

      

    StackStatus -> (string)

      

      The current status of the stack.

      

      

    StackStatusReason -> (string)

      

      Success/Failure message associated with the stack status.

      

      

    

  

NextToken -> (string)

  

  If the output exceeds 1 MB in size, a string that identifies the next page of stacks. If no additional page exists, this value is null.

  

  

