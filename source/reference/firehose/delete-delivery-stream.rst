[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose delete-delivery-stream:


**********************
delete-delivery-stream
**********************



===========
Description
===========



Deletes a delivery stream and its data.

 

You can delete a delivery stream only if it is in ``ACTIVE`` or ``DELETING`` state, and not in the ``CREATING`` state. While the deletion request is in process, the delivery stream is in the ``DELETING`` state.

 

To check the state of a delivery stream, use  describe-delivery-stream .

 

While the delivery stream is ``DELETING`` state, the service may continue to accept the records, but the service doesn't make any guarantees with respect to delivering the data. Therefore, as a best practice, you should first stop any applications that are sending records before deleting a delivery stream.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/firehose-2015-08-04/DeleteDeliveryStream>`_


========
Synopsis
========

::

    delete-delivery-stream
  --delivery-stream-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

