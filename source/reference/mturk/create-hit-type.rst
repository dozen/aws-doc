[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk create-hit-type:


***************
create-hit-type
***************



===========
Description
===========



The ``create-hit-type`` operation creates a new HIT type. This operation allows you to define a standard set of HIT properties to use when creating HITs. If you register a HIT type with values that match an existing HIT type, the HIT type ID of the existing type will be returned. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/CreateHITType>`_


========
Synopsis
========

::

    create-hit-type
  [--auto-approval-delay-in-seconds <value>]
  --assignment-duration-in-seconds <value>
  --reward <value>
  --title <value>
  [--keywords <value>]
  --description <value>
  [--qualification-requirements <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-approval-delay-in-seconds`` (long)


  The number of seconds after an assignment for the HIT has been submitted, after which the assignment is considered Approved automatically unless the Requester explicitly rejects it. 

  

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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HITTypeId -> (string)

  

  The ID of the newly registered HIT type.

  

  

