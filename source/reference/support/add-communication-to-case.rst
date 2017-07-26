[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support add-communication-to-case:


*************************
add-communication-to-case
*************************



===========
Description
===========



Adds additional customer communication to an AWS Support case. You use the ``caseId`` value to identify the case to add communication to. You can list a set of email addresses to copy on the communication using the ``ccEmailAddresses`` value. The ``communicationBody`` value contains the text of the communication.

 

The response indicates the success or failure of the request.

 

This operation implements a subset of the features of the AWS Support Center.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/AddCommunicationToCase>`_


========
Synopsis
========

::

    add-communication-to-case
  [--case-id <value>]
  --communication-body <value>
  [--cc-email-addresses <value>]
  [--attachment-set-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--case-id`` (string)


  The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47*  

  

``--communication-body`` (string)


  The body of an email communication to add to the support case.

  

``--cc-email-addresses`` (list)


  The email addresses in the CC line of an email to be added to the support case.

  



Syntax::

  "string" "string" ...



``--attachment-set-id`` (string)


  The ID of a set of one or more attachments for the communication to add to the case. Create the set by calling  add-attachments-to-set  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

result -> (boolean)

  

  True if  add-communication-to-case succeeds. Otherwise, returns an error.

  

  

