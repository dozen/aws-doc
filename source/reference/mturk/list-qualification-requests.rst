[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk list-qualification-requests:


***************************
list-qualification-requests
***************************



===========
Description
===========



The ``list-qualification-requests`` operation retrieves requests for Qualifications of a particular Qualification type. The owner of the Qualification type calls this operation to poll for pending requests, and accepts them using the AcceptQualification operation. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/ListQualificationRequests>`_


========
Synopsis
========

::

    list-qualification-requests
  [--qualification-type-id <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-type-id`` (string)


  The ID of the QualificationType.

  

``--next-token`` (string)


  If the previous response was incomplete (because there is more data to retrieve), Amazon Mechanical Turk returns a pagination token in the response. You can use this pagination token to retrieve the next set of results. 

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NumResults -> (integer)

  

  The number of Qualification requests on this page in the filtered results list, equivalent to the number of Qualification requests being returned by this call.

  

  

NextToken -> (string)

  

  If the previous response was incomplete (because there is more data to retrieve), Amazon Mechanical Turk returns a pagination token in the response. You can use this pagination token to retrieve the next set of results. 

  

  

QualificationRequests -> (list)

  

  The Qualification request. The response includes one QualificationRequest element for each Qualification request returned by the query.

  

  (structure)

    

    The QualificationRequest data structure represents a request a Worker has made for a Qualification. 

    

    QualificationRequestId -> (string)

      

      The ID of the Qualification request, a unique identifier generated when the request was submitted. 

      

      

    QualificationTypeId -> (string)

      

      The ID of the Qualification type the Worker is requesting, as returned by the create-qualification-type operation. 

      

      

    WorkerId -> (string)

      

      The ID of the Worker requesting the Qualification.

      

      

    Test -> (string)

      

      The contents of the Qualification test that was presented to the Worker, if the type has a test and the Worker has submitted answers. This value is identical to the QuestionForm associated with the Qualification type at the time the Worker requests the Qualification.

      

      

    Answer -> (string)

      

      The Worker's answers for the Qualification type's test contained in a QuestionFormAnswers document, if the type has a test and the Worker has submitted answers. If the Worker does not provide any answers, Answer may be empty. 

      

      

    SubmitTime -> (timestamp)

      

      The date and time the Qualification request had a status of Submitted. This is either the time the Worker submitted answers for a Qualification test, or the time the Worker requested the Qualification if the Qualification type does not have a test. 

      

      

    

  

