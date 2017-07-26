[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk list-hits-for-qualification-type:


********************************
list-hits-for-qualification-type
********************************



===========
Description
===========



The ``list-hits-for-qualification-type`` operation returns the HITs that use the given Qualification type for a Qualification requirement. The operation returns HITs of any status, except for HITs that have been deleted with the ``delete-hit`` operation or that have been auto-deleted. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/ListHITsForQualificationType>`_


========
Synopsis
========

::

    list-hits-for-qualification-type
  --qualification-type-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-type-id`` (string)


  The ID of the Qualification type to use when querying HITs. 

  

``--next-token`` (string)


  Pagination Token

  

``--max-results`` (integer)


  Limit the number of results returned. 

  

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

  

  The number of HITs on this page in the filtered results list, equivalent to the number of HITs being returned by this call. 

  

  

HITs -> (list)

  

  The list of HIT elements returned by the query.

  

  (structure)

    

    The HIT data structure represents a single HIT, including all the information necessary for a Worker to accept and complete the HIT.

    

    HITId -> (string)

      

      A unique identifier for the HIT.

      

      

    HITTypeId -> (string)

      

      The ID of the HIT type of this HIT

      

      

    HITGroupId -> (string)

      

      The ID of the HIT Group of this HIT.

      

      

    HITLayoutId -> (string)

      

      The ID of the HIT Layout of this HIT.

      

      

    CreationTime -> (timestamp)

      

      The date and time the HIT was created.

      

      

    Title -> (string)

      

      The title of the HIT.

      

      

    Description -> (string)

      

      A general description of the HIT.

      

      

    Question -> (string)

      

      The data the Worker completing the HIT uses produce the results. This is either either a QuestionForm, HTMLQuestion or an ExternalQuestion data structure.

      

      

    Keywords -> (string)

      

      One or more words or phrases that describe the HIT, separated by commas. Search terms similar to the keywords of a HIT are more likely to have the HIT in the search results.

      

      

    HITStatus -> (string)

      

      The status of the HIT and its assignments. Valid Values are Assignable | Unassignable | Reviewable | Reviewing | Disposed. 

      

      

    MaxAssignments -> (integer)

      

      The number of times the HIT can be accepted and completed before the HIT becomes unavailable. 

      

      

    Reward -> (string)

      

      A string representing a numeric value.

      

      

    AutoApprovalDelayInSeconds -> (long)

      

      The amount of time, in seconds, after the Worker submits an assignment for the HIT that the results are automatically approved by Amazon Mechanical Turk. This is the amount of time the Requester has to reject an assignment submitted by a Worker before the assignment is auto-approved and the Worker is paid. 

      

      

    Expiration -> (timestamp)

      

      The date and time the HIT expires.

      

      

    AssignmentDurationInSeconds -> (long)

      

      The length of time, in seconds, that a Worker has to complete the HIT after accepting it.

      

      

    RequesterAnnotation -> (string)

      

      An arbitrary data field the Requester who created the HIT can use. This field is visible only to the creator of the HIT.

      

      

    QualificationRequirements -> (list)

      

      A condition that a Worker's Qualifications must meet in order to accept the HIT. A HIT can have between zero and ten Qualification requirements. All requirements must be met by a Worker's Qualifications for the Worker to accept the HIT.

      

      (structure)

        

        The QualificationRequirement data structure describes a Qualification that a Worker must have before the Worker is allowed to accept a HIT. A requirement may optionally state that a Worker must have the Qualification in order to preview the HIT. 

        

        QualificationTypeId -> (string)

          

          The ID of the Qualification type for the requirement.

          

          

        Comparator -> (string)

          

          The kind of comparison to make against a Qualification's value. You can compare a Qualification's value to an IntegerValue to see if it is LessThan, LessThanOrEqualTo, GreaterThan, GreaterThanOrEqualTo, EqualTo, or NotEqualTo the IntegerValue. You can compare it to a LocaleValue to see if it is EqualTo, or NotEqualTo the LocaleValue. You can check to see if the value is In or NotIn a set of IntegerValue or LocaleValue values. Lastly, a Qualification requirement can also test if a Qualification Exists or DoesNotExist in the user's profile, regardless of its value. 

          

          

        IntegerValues -> (list)

          

          The integer value to compare against the Qualification's value. IntegerValue must not be present if Comparator is Exists or DoesNotExist. IntegerValue can only be used if the Qualification type has an integer value; it cannot be used with the Worker_Locale QualificationType ID. When performing a set comparison by using the In or the NotIn comparator, you can use up to 15 IntegerValue elements in a QualificationRequirement data structure. 

          

          (integer)

            

            

          

        LocaleValues -> (list)

          

          The locale value to compare against the Qualification's value. The local value must be a valid ISO 3166 country code or supports ISO 3166-2 subdivisions. LocaleValue can only be used with a Worker_Locale QualificationType ID. LocaleValue can only be used with the EqualTo, NotEqualTo, In, and NotIn comparators. You must only use a single LocaleValue element when using the EqualTo or NotEqualTo comparators. When performing a set comparison by using the In or the NotIn comparator, you can use up to 30 LocaleValue elements in a QualificationRequirement data structure. 

          

          (structure)

            

            The Locale data structure represents a geographical region or location.

            

            Country -> (string)

              

              The country of the locale. Must be a valid ISO 3166 country code. For example, the code US refers to the United States of America. 

              

              

            Subdivision -> (string)

              

              The state or subdivision of the locale. A valid ISO 3166-2 subdivision code. For example, the code WA refers to the state of Washington.

              

              

            

          

        RequiredToPreview -> (boolean)

          

          If true, the question data for the HIT will not be shown when a Worker whose Qualifications do not meet this requirement tries to preview the HIT. That is, a Worker's Qualifications must meet all of the requirements for which RequiredToPreview is true in order to preview the HIT. If a Worker meets all of the requirements where RequiredToPreview is true (or if there are no such requirements), but does not meet all of the requirements for the HIT, the Worker will be allowed to preview the HIT's question data, but will not be allowed to accept and complete the HIT. The default is false. 

          

          

        

      

    HITReviewStatus -> (string)

      

      Indicates the review status of the HIT. Valid Values are NotReviewed | MarkedForReview | ReviewedAppropriate | ReviewedInappropriate.

      

      

    NumberOfAssignmentsPending -> (integer)

      

      The number of assignments for this HIT that are being previewed or have been accepted by Workers, but have not yet been submitted, returned, or abandoned.

      

      

    NumberOfAssignmentsAvailable -> (integer)

      

      The number of assignments for this HIT that are available for Workers to accept.

      

      

    NumberOfAssignmentsCompleted -> (integer)

      

      The number of assignments for this HIT that have been approved or rejected.

      

      

    

  

