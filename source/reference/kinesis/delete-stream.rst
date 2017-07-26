[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis delete-stream:


*************
delete-stream
*************



===========
Description
===========



Deletes an Amazon Kinesis stream and all its shards and data. You must shut down any applications that are operating on the stream before you delete the stream. If an application attempts to operate on a deleted stream, it will receive the exception ``ResourceNotFoundException`` .

 

If the stream is in the ``ACTIVE`` state, you can delete it. After a ``delete-stream`` request, the specified stream is in the ``DELETING`` state until Amazon Kinesis completes the deletion.

 

 **Note:** Amazon Kinesis might continue to accept data read and write operations, such as  put-record ,  put-records , and  get-records , on a stream in the ``DELETING`` state until the stream deletion is complete.

 

When you delete a stream, any shards in that stream are also deleted, and any tags are dissociated from the stream.

 

You can use the  describe-stream operation to check the state of the stream, which is returned in ``StreamStatus`` .

 

  delete-stream has a limit of 5 transactions per second per account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/DeleteStream>`_


========
Synopsis
========

::

    delete-stream
  --stream-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None