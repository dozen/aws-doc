[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk delete-qualification-type:


*************************
delete-qualification-type
*************************



===========
Description
===========



The ``delete-qualification-type`` deletes a Qualification type and deletes any HIT types that are associated with the Qualification type. 

 

This operation does not revoke Qualifications already assigned to Workers because the Qualifications might be needed for active HITs. If there are any pending requests for the Qualification type, Amazon Mechanical Turk rejects those requests. After you delete a Qualification type, you can no longer use it to create HITs or HIT types.

 

.. note::

   

  delete-qualification-type must wait for all the HITs that use the deleted Qualification type to be deleted before completing. It may take up to 48 hours before delete-qualification-type completes and the unique name of the Qualification type is available for reuse with CreateQualificationType.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/DeleteQualificationType>`_


========
Synopsis
========

::

    delete-qualification-type
  --qualification-type-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-type-id`` (string)


  The ID of the QualificationType to dispose.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

