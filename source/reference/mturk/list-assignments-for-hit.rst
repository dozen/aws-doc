[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk list-assignments-for-hit:


************************
list-assignments-for-hit
************************



===========
Description
===========



The ``list-assignments-for-hit`` operation retrieves completed assignments for a HIT. You can use this operation to retrieve the results for a HIT. 

 

You can get assignments for a HIT at any time, even if the HIT is not yet Reviewable. If a HIT requested multiple assignments, and has received some results but has not yet become Reviewable, you can still retrieve the partial results with this operation. 

 

Use the AssignmentStatus parameter to control which set of assignments for a HIT are returned. The list-assignments-for-hit operation can return submitted assignments awaiting approval, or it can return assignments that have already been approved or rejected. You can set AssignmentStatus=Approved,Rejected to get assignments that have already been approved and rejected together in one result set. 

 

Only the Requester who created the HIT can retrieve the assignments for that HIT. 

 

Results are sorted and divided into numbered pages and the operation returns a single page of results. You can use the parameters of the operation to control sorting and pagination. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/ListAssignmentsForHIT>`_


========
Synopsis
========

::

    list-assignments-for-hit
  --hit-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--assignment-statuses <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hit-id`` (string)


  The ID of the HIT.

  

``--next-token`` (string)


  Pagination token

  

``--max-results`` (integer)


``--assignment-statuses`` (list)


  The status of the assignments to return: Submitted | Approved | Rejected

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Submitted
    Approved
    Rejected





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextToken -> (string)

  

  If the previous response was incomplete (because there is more data to retrieve), Amazon Mechanical Turk returns a pagination token in the response. You can use this pagination token to retrieve the next set of results. 

  

  

NumResults -> (integer)

  

  The number of assignments on the page in the filtered results list, equivalent to the number of assignments returned by this call.

  

  

Assignments -> (list)

  

  The collection of Assignment data structures returned by this call.

  

  (structure)

    

    The Assignment data structure represents a single assignment of a HIT to a Worker. The assignment tracks the Worker's efforts to complete the HIT, and contains the results for later retrieval. 

    

    AssignmentId -> (string)

      

      A unique identifier for the assignment.

      

      

    WorkerId -> (string)

      

      The ID of the Worker who accepted the HIT.

      

      

    HITId -> (string)

      

      The ID of the HIT.

      

      

    AssignmentStatus -> (string)

      

      The status of the assignment.

      

      

    AutoApprovalTime -> (timestamp)

      

      If results have been submitted, AutoApprovalTime is the date and time the results of the assignment results are considered Approved automatically if they have not already been explicitly approved or rejected by the Requester. This value is derived from the auto-approval delay specified by the Requester in the HIT. This value is omitted from the assignment if the Worker has not yet submitted results.

      

      

    AcceptTime -> (timestamp)

      

      The date and time the Worker accepted the assignment.

      

      

    SubmitTime -> (timestamp)

      

      If the Worker has submitted results, SubmitTime is the date and time the assignment was submitted. This value is omitted from the assignment if the Worker has not yet submitted results.

      

      

    ApprovalTime -> (timestamp)

      

      If the Worker has submitted results and the Requester has approved the results, ApprovalTime is the date and time the Requester approved the results. This value is omitted from the assignment if the Requester has not yet approved the results.

      

      

    RejectionTime -> (timestamp)

      

      If the Worker has submitted results and the Requester has rejected the results, RejectionTime is the date and time the Requester rejected the results.

      

      

    Deadline -> (timestamp)

      

      The date and time of the deadline for the assignment. This value is derived from the deadline specification for the HIT and the date and time the Worker accepted the HIT.

      

      

    Answer -> (string)

      

      The Worker's answers submitted for the HIT contained in a QuestionFormAnswers document, if the Worker provides an answer. If the Worker does not provide any answers, Answer may contain a QuestionFormAnswers document, or Answer may be empty.

      

      

    RequesterFeedback -> (string)

      

      The feedback string included with the call to the approve-assignment operation or the reject-assignment operation, if the Requester approved or rejected the assignment and specified feedback.

      

      

    

  

