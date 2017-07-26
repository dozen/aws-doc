[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk get-qualification-score:


***********************
get-qualification-score
***********************



===========
Description
===========



The ``get-qualification-score`` operation returns the value of a Worker's Qualification for a given Qualification type. 

 

To get a Worker's Qualification, you must know the Worker's ID. The Worker's ID is included in the assignment data returned by the ``list-assignments-for-hit`` operation. 

 

Only the owner of a Qualification type can query the value of a Worker's Qualification of that type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/GetQualificationScore>`_


========
Synopsis
========

::

    get-qualification-score
  --qualification-type-id <value>
  --worker-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-type-id`` (string)


  The ID of the QualificationType.

  

``--worker-id`` (string)


  The ID of the Worker whose Qualification is being updated.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Qualification -> (structure)

  

  The Qualification data structure of the Qualification assigned to a user, including the Qualification type and the value (score). 

  

  QualificationTypeId -> (string)

    

    The ID of the Qualification type for the Qualification.

    

    

  WorkerId -> (string)

    

    The ID of the Worker who possesses the Qualification. 

    

    

  GrantTime -> (timestamp)

    

    The date and time the Qualification was granted to the Worker. If the Worker's Qualification was revoked, and then re-granted based on a new Qualification request, GrantTime is the date and time of the last call to the accept-qualification-request operation.

    

    

  IntegerValue -> (integer)

    

    The value (score) of the Qualification, if the Qualification has an integer value.

    

    

  LocaleValue -> (structure)

    

    The Locale data structure represents a geographical region or location.

    

    Country -> (string)

      

      The country of the locale. Must be a valid ISO 3166 country code. For example, the code US refers to the United States of America. 

      

      

    Subdivision -> (string)

      

      The state or subdivision of the locale. A valid ISO 3166-2 subdivision code. For example, the code WA refers to the state of Washington.

      

      

    

  Status -> (string)

    

    The status of the Qualification. Valid values are Granted | Revoked.

    

    

  

