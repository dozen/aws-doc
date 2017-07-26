[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk get-qualification-type:


**********************
get-qualification-type
**********************



===========
Description
===========



The ``get-qualification-type`` operation retrieves information about a Qualification type using its ID. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/GetQualificationType>`_


========
Synopsis
========

::

    get-qualification-type
  --qualification-type-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-type-id`` (string)


  The ID of the QualificationType.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

QualificationType -> (structure)

  

  The returned Qualification Type

  

  QualificationTypeId -> (string)

    

    A unique identifier for the Qualification type. A Qualification type is given a Qualification type ID when you call the create-qualification-type operation. 

    

    

  CreationTime -> (timestamp)

    

    The date and time the Qualification type was created. 

    

    

  Name -> (string)

    

    The name of the Qualification type. The type name is used to identify the type, and to find the type using a Qualification type search. 

    

    

  Description -> (string)

    

    A long description for the Qualification type. 

    

    

  Keywords -> (string)

    

    One or more words or phrases that describe theQualification type, separated by commas. The Keywords make the type easier to find using a search. 

    

    

  QualificationTypeStatus -> (string)

    

    The status of the Qualification type. A Qualification type's status determines if users can apply to receive a Qualification of this type, and if HITs can be created with requirements based on this type. Valid values are Active | Inactive. 

    

    

  Test -> (string)

    

    The questions for a Qualification test associated with this Qualification type that a user can take to obtain a Qualification of this type. This parameter must be specified if AnswerKey is present. A Qualification type cannot have both a specified Test parameter and an AutoGranted value of true. 

    

    

  TestDurationInSeconds -> (long)

    

    The amount of time, in seconds, given to a Worker to complete the Qualification test, beginning from the time the Worker requests the Qualification. 

    

    

  AnswerKey -> (string)

    

    The answers to the Qualification test specified in the Test parameter.

    

    

  RetryDelayInSeconds -> (long)

    

    The amount of time, in seconds, Workers must wait after taking the Qualification test before they can take it again. Workers can take a Qualification test multiple times if they were not granted the Qualification from a previous attempt, or if the test offers a gradient score and they want a better score. If not specified, retries are disabled and Workers can request a Qualification only once. 

    

    

  IsRequestable -> (boolean)

    

    Specifies whether the Qualification type is one that a user can request through the Amazon Mechanical Turk web site, such as by taking a Qualification test. This value is False for Qualifications assigned automatically by the system. Valid values are True | False. 

    

    

  AutoGranted -> (boolean)

    

    Specifies that requests for the Qualification type are granted immediately, without prompting the Worker with a Qualification test. Valid values are True | False.

    

    

  AutoGrantedValue -> (integer)

    

    The Qualification integer value to use for automatically granted Qualifications, if AutoGranted is true. This is 1 by default. 

    

    

  

