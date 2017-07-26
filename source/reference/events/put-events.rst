[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events put-events:


**********
put-events
**********



===========
Description
===========



Sends custom events to Amazon CloudWatch Events so that they can be matched to rules.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/PutEvents>`_


========
Synopsis
========

::

    put-events
  --entries <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To send a custom event to CloudWatch Events**

This example sends a custom event to CloudWatch Events. The event is contained within the putevents.json file::

  aws events put-events --entries file://putevents.json            

Here are the contents of the putevents.json file::

  [
    {
      "Source": "com.mycompany.myapp",
      "Detail": "{ \"key1\": \"value1\", \"key2\": \"value2\" }",
      "Resources": [
        "resource1",
        "resource2"
      ],
      "DetailType": "myDetailType"
    },
    {
      "Source": "com.mycompany.myapp",
      "Detail": "{ \"key1\": \"value3\", \"key2\": \"value4\" }",
      "Resources": [
        "resource1",
        "resource2"
      ],
      "DetailType": "myDetailType"
     }
  ]


======
Output
======

FailedEntryCount -> (integer)

  

  The number of failed entries.

  

  

Entries -> (list)

  

  The successfully and unsuccessfully ingested events results. If the ingestion was successful, the entry has the event ID in it. Otherwise, you can use the error code and error message to identify the problem with the entry.

  

  (structure)

    

    Represents an event that failed to be submitted.

    

    EventId -> (string)

      

      The ID of the event.

      

      

    ErrorCode -> (string)

      

      The error code that indicates why the event submission failed.

      

      

    ErrorMessage -> (string)

      

      The error message that explains why the event submission failed.

      

      

    

  

