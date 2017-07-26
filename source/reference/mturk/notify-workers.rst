[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk notify-workers:


**************
notify-workers
**************



===========
Description
===========



The ``notify-workers`` operation sends an email to one or more Workers that you specify with the Worker ID. You can specify up to 100 Worker IDs to send the same message with a single call to the notify-workers operation. The notify-workers operation will send a notification email to a Worker only if you have previously approved or rejected work from the Worker. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/NotifyWorkers>`_


========
Synopsis
========

::

    notify-workers
  --subject <value>
  --message-text <value>
  --worker-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subject`` (string)


  The subject line of the email message to send. Can include up to 200 characters.

  

``--message-text`` (string)


  The text of the email message to send. Can include up to 4,096 characters

  

``--worker-ids`` (list)


  A list of Worker IDs you wish to notify. You can notify upto 100 Workers at a time.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NotifyWorkersFailureStatuses -> (list)

  

  When MTurk sends notifications to the list of Workers, it returns back any failures it encounters in this list of NotifyWorkersFailureStatus objects. 

  

  (structure)

    

    When MTurk encounters an issue with notifying the Workers you specified, it returns back this object with failure details. 

    

    NotifyWorkersFailureCode -> (string)

      

      Encoded value for the failure type. 

      

      

    NotifyWorkersFailureMessage -> (string)

      

      A message detailing the reason the Worker could not be notified. 

      

      

    WorkerId -> (string)

      

      The ID of the Worker.

      

      

    

  

