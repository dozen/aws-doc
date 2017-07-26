[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support add-attachments-to-set:


**********************
add-attachments-to-set
**********************



===========
Description
===========



Adds one or more attachments to an attachment set. If an ``attachmentSetId`` is not specified, a new attachment set is created, and the ID of the set is returned in the response. If an ``attachmentSetId`` is specified, the attachments are added to the specified set, if it exists.

 

An attachment set is a temporary container for attachments that are to be added to a case or case communication. The set is available for one hour after it is created; the ``expiryTime`` returned in the response indicates when the set expires. The maximum number of attachments in a set is 3, and the maximum size of any attachment in the set is 5 MB.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/AddAttachmentsToSet>`_


========
Synopsis
========

::

    add-attachments-to-set
  [--attachment-set-id <value>]
  --attachments <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attachment-set-id`` (string)


  The ID of the attachment set. If an ``attachmentSetId`` is not specified, a new attachment set is created, and the ID of the set is returned in the response. If an ``attachmentSetId`` is specified, the attachments are added to the specified set, if it exists.

  

``--attachments`` (list)


  One or more attachments to add to the set. The limit is 3 attachments per set, and the size limit is 5 MB per attachment.

  



Shorthand Syntax::

    fileName=string,data=blob ...




JSON Syntax::

  [
    {
      "fileName": "string",
      "data": blob
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

attachmentSetId -> (string)

  

  The ID of the attachment set. If an ``attachmentSetId`` was not specified, a new attachment set is created, and the ID of the set is returned in the response. If an ``attachmentSetId`` was specified, the attachments are added to the specified set, if it exists.

  

  

expiryTime -> (string)

  

  The time and date when the attachment set expires.

  

  

