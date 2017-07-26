[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose list-delivery-streams:


*********************
list-delivery-streams
*********************



===========
Description
===========



Lists your delivery streams.

 

The number of delivery streams might be too large to return using a single call to  list-delivery-streams . You can limit the number of delivery streams returned, using the **Limit** parameter. To determine whether there are more delivery streams to list, check the value of **HasMoreDeliveryStreams** in the output. If there are more delivery streams to list, you can request them by specifying the name of the last delivery stream returned in the call in the **ExclusiveStartDeliveryStreamName** parameter of a subsequent call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/firehose-2015-08-04/ListDeliveryStreams>`_


========
Synopsis
========

::

    list-delivery-streams
  [--limit <value>]
  [--exclusive-start-delivery-stream-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--limit`` (integer)


  The maximum number of delivery streams to list.

  

``--exclusive-start-delivery-stream-name`` (string)


  The name of the delivery stream to start the list with.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DeliveryStreamNames -> (list)

  

  The names of the delivery streams.

  

  (string)

    

    

  

HasMoreDeliveryStreams -> (boolean)

  

  Indicates whether there are more delivery streams available to list.

  

  

