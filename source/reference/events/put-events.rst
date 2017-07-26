[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events put-events:


**********
put-events
**********



===========
Description
===========



Sends custom events to Amazon CloudWatch Events so that they can be matched to rules.



========
Synopsis
========

::

    put-events
  --entries <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--entries`` (list)


  The entry that defines an event in your system. You can specify several parameters for the entry such as the source and type of the event, resources associated with the event, and so on.

  



Shorthand Syntax::

    Time=timestamp,Source=string,Resources=string,string,DetailType=string,Detail=string ...




JSON Syntax::

  [
    {
      "Time": timestamp,
      "Source": "string",
      "Resources": ["string", ...],
      "DetailType": "string",
      "Detail": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FailedEntryCount -> (integer)

  

  The number of failed entries.

  

  

Entries -> (list)

  

  A list of successfully and unsuccessfully ingested events results. If the ingestion was successful, the entry will have the event ID in it. If not, then the ErrorCode and ErrorMessage can be used to identify the problem with the entry.

  

  (structure)

    

    A PutEventsResult contains a list of PutEventsResultEntry.

    

    EventId -> (string)

      

      The ID of the event submitted to Amazon CloudWatch Events.

      

      

    ErrorCode -> (string)

      

      The error code representing why the event submission failed on this entry.

      

      

    ErrorMessage -> (string)

      

      The error message explaining why the event submission failed on this entry.

      

      

    

  

