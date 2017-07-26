[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline put-approval-result:


*******************
put-approval-result
*******************



===========
Description
===========



Provides the response to a manual approval request to AWS CodePipeline. Valid responses include Approved and Rejected.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/PutApprovalResult>`_


========
Synopsis
========

::

    put-approval-result
  --pipeline-name <value>
  --stage-name <value>
  --action-name <value>
  --result <value>
  --token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-name`` (string)


  The name of the pipeline that contains the action. 

  

``--stage-name`` (string)


  The name of the stage that contains the action.

  

``--action-name`` (string)


  The name of the action for which approval is requested.

  

``--result`` (structure)


  Represents information about the result of the approval request.

  



Shorthand Syntax::

    summary=string,status=string




JSON Syntax::

  {
    "summary": "string",
    "status": "Approved"|"Rejected"
  }



``--token`` (string)


  The system-generated token used to identify a unique approval request. The token for each open approval request can be obtained using the  get-pipeline-state action and is used to validate that the approval request corresponding to this token is still valid.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

approvedAt -> (timestamp)

  

  The timestamp showing when the approval or rejection was submitted.

  

  

