[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose list-delivery-streams:


*********************
list-delivery-streams
*********************



===========
Description
===========



Lists your delivery streams.

 

The number of delivery streams might be too large to return using a single call to  list-delivery-streams . You can limit the number of delivery streams returned, using the ``Limit`` parameter. To determine whether there are more delivery streams to list, check the value of ``HasMoreDeliveryStreams`` in the output. If there are more delivery streams to list, you can request them by specifying the name of the last delivery stream returned in the call in the ``ExclusiveStartDeliveryStreamName`` parameter of a subsequent call.



========
Synopsis
========

::

    list-delivery-streams
  [--limit <value>]
  [--exclusive-start-delivery-stream-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--limit`` (integer)


  The maximum number of delivery streams to list.

  

``--exclusive-start-delivery-stream-name`` (string)


  The name of the delivery stream to start the list with.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DeliveryStreamNames -> (list)

  

  The names of the delivery streams.

  

  (string)

    

    

  

HasMoreDeliveryStreams -> (boolean)

  

  Indicates whether there are more delivery streams available to list.

  

  

