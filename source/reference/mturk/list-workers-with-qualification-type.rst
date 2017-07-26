[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk list-workers-with-qualification-type:


************************************
list-workers-with-qualification-type
************************************



===========
Description
===========



The ``list-workers-with-qualification-type`` operation returns all of the Workers that have been associated with a given Qualification type. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/ListWorkersWithQualificationType>`_


========
Synopsis
========

::

    list-workers-with-qualification-type
  --qualification-type-id <value>
  [--status <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-type-id`` (string)


  The ID of the Qualification type of the Qualifications to return.

  

``--status`` (string)


  The status of the Qualifications to return. Can be ``Granted | Revoked`` . 

  

  Possible values:

  
  *   ``Granted``

  
  *   ``Revoked``

  

  

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

  

  The number of Qualifications on this page in the filtered results list, equivalent to the number of Qualifications being returned by this call.

  

  

Qualifications -> (list)

  

  The list of Qualification elements returned by this call. 

  

  (structure)

    

    The Qualification data structure represents a Qualification assigned to a user, including the Qualification type and the value (score).

    

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

      

      

    

  

