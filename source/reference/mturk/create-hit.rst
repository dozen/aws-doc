[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk create-hit:


**********
create-hit
**********



===========
Description
===========



The ``create-hit`` operation creates a new Human Intelligence Task (HIT). The new HIT is made available for Workers to find and accept on the Amazon Mechanical Turk website. 

 

This operation allows you to specify a new HIT by passing in values for the properties of the HIT, such as its title, reward amount and number of assignments. When you pass these values to ``create-hit`` , a new HIT is created for you, with a new ``HITTypeID`` . The HITTypeID can be used to create additional HITs in the future without needing to specify common parameters such as the title, description and reward amount each time.

 

An alternative way to create HITs is to first generate a HITTypeID using the ``create-hit-type`` operation and then call the ``create-hit-with-hit-type`` operation. This is the recommended best practice for Requesters who are creating large numbers of HITs. 

 

create-hit also supports several ways to provide question data: by providing a value for the ``Question`` parameter that fully specifies the contents of the HIT, or by providing a ``HitLayoutId`` and associated ``HitLayoutParameters`` . 

 

.. note::

   

  If a HIT is created with 10 or more maximum assignments, there is an additional fee. For more information, see `Amazon Mechanical Turk Pricing <https://requester.mturk.com/pricing>`_ .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/CreateHIT>`_


========
Synopsis
========

::

    create-hit
  [--max-assignments <value>]
  [--auto-approval-delay-in-seconds <value>]
  --lifetime-in-seconds <value>
  --assignment-duration-in-seconds <value>
  --reward <value>
  --title <value>
  [--keywords <value>]
  --description <value>
  [--question <value>]
  [--requester-annotation <value>]
  [--qualification-requirements <value>]
  [--unique-request-token <value>]
  [--assignment-review-policy <value>]
  [--hit-review-policy <value>]
  [--hit-layout-id <value>]
  [--hit-layout-parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-assignments`` (integer)


  The number of times the HIT can be accepted and completed before the HIT becomes unavailable. 

  

``--auto-approval-delay-in-seconds`` (long)


  The number of seconds after an assignment for the HIT has been submitted, after which the assignment is considered Approved automatically unless the Requester explicitly rejects it. 

  

``--lifetime-in-seconds`` (long)


  An amount of time, in seconds, after which the HIT is no longer available for users to accept. After the lifetime of the HIT elapses, the HIT no longer appears in HIT searches, even if not all of the assignments for the HIT have been accepted. 

  

``--assignment-duration-in-seconds`` (long)


  The amount of time, in seconds, that a Worker has to complete the HIT after accepting it. If a Worker does not complete the assignment within the specified duration, the assignment is considered abandoned. If the HIT is still active (that is, its lifetime has not elapsed), the assignment becomes available for other users to find and accept. 

  

``--reward`` (string)


  The amount of money the Requester will pay a Worker for successfully completing the HIT. 

  

``--title`` (string)


  The title of the HIT. A title should be short and descriptive about the kind of task the HIT contains. On the Amazon Mechanical Turk web site, the HIT title appears in search results, and everywhere the HIT is mentioned. 

  

``--keywords`` (string)


  One or more words or phrases that describe the HIT, separated by commas. These words are used in searches to find HITs. 

  

``--description`` (string)


  A general description of the HIT. A description includes detailed information about the kind of task the HIT contains. On the Amazon Mechanical Turk web site, the HIT description appears in the expanded view of search results, and in the HIT and assignment screens. A good description gives the user enough information to evaluate the HIT before accepting it. 

  

``--question`` (string)


  The data the person completing the HIT uses to produce the results. 

   

  Constraints: Must be a QuestionForm data structure, an ExternalQuestion data structure, or an HTMLQuestion data structure. The XML question data must not be larger than 64 kilobytes (65,535 bytes) in size, including whitespace. 

   

  Either a Question parameter or a HITLayoutId parameter must be provided.

  

``--requester-annotation`` (string)


  An arbitrary data field. The RequesterAnnotation parameter lets your application attach arbitrary data to the HIT for tracking purposes. For example, this parameter could be an identifier internal to the Requester's application that corresponds with the HIT. 

   

  The RequesterAnnotation parameter for a HIT is only visible to the Requester who created the HIT. It is not shown to the Worker, or any other Requester. 

   

  The RequesterAnnotation parameter may be different for each HIT you submit. It does not affect how your HITs are grouped. 

  

``--qualification-requirements`` (list)


  A condition that a Worker's Qualifications must meet before the Worker is allowed to accept and complete the HIT. 

  



Shorthand Syntax::

    QualificationTypeId=string,Comparator=string,IntegerValues=integer,integer,LocaleValues=[{Country=string,Subdivision=string},{Country=string,Subdivision=string}],RequiredToPreview=boolean ...




JSON Syntax::

  [
    {
      "QualificationTypeId": "string",
      "Comparator": "LessThan"|"LessThanOrEqualTo"|"GreaterThan"|"GreaterThanOrEqualTo"|"EqualTo"|"NotEqualTo"|"Exists"|"DoesNotExist"|"In"|"NotIn",
      "IntegerValues": [integer, ...],
      "LocaleValues": [
        {
          "Country": "string",
          "Subdivision": "string"
        }
        ...
      ],
      "RequiredToPreview": true|false
    }
    ...
  ]



``--unique-request-token`` (string)


  A unique identifier for this request which allows you to retry the call on error without creating duplicate HITs. This is useful in cases such as network timeouts where it is unclear whether or not the call succeeded on the server. If the HIT already exists in the system from a previous call using the same UniqueRequestToken, subsequent calls will return a AWS.MechanicalTurk.HitAlreadyExists error with a message containing the HITId. 

   

  .. note::

     

    Note: It is your responsibility to ensure uniqueness of the token. The unique token expires after 24 hours. Subsequent calls using the same UniqueRequestToken made after the 24 hour limit could create duplicate HITs. 

     

  

``--assignment-review-policy`` (structure)


  The Assignment-level Review Policy applies to the assignments under the HIT. You can specify for Mechanical Turk to take various actions based on the policy. 

  



JSON Syntax::

  {
    "PolicyName": "string",
    "Parameters": [
      {
        "Key": "string",
        "Values": ["string", ...],
        "MapEntries": [
          {
            "Key": "string",
            "Values": ["string", ...]
          }
          ...
        ]
      }
      ...
    ]
  }



``--hit-review-policy`` (structure)


  The HIT-level Review Policy applies to the HIT. You can specify for Mechanical Turk to take various actions based on the policy. 

  



JSON Syntax::

  {
    "PolicyName": "string",
    "Parameters": [
      {
        "Key": "string",
        "Values": ["string", ...],
        "MapEntries": [
          {
            "Key": "string",
            "Values": ["string", ...]
          }
          ...
        ]
      }
      ...
    ]
  }



``--hit-layout-id`` (string)


  The HITLayoutId allows you to use a pre-existing HIT design with placeholder values and create an additional HIT by providing those values as HITLayoutParameters. 

   

  Constraints: Either a Question parameter or a HITLayoutId parameter must be provided. 

  

``--hit-layout-parameters`` (list)


  If the HITLayoutId is provided, any placeholder values must be filled in with values using the HITLayoutParameter structure. For more information, see HITLayout. 

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HIT -> (structure)

  

  Contains the newly created HIT data. For a description of the HIT data structure as it appears in responses, see the HIT Data Structure documentation. 

  

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

    

    

  

