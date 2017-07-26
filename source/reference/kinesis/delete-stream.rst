[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis delete-stream:


*************
delete-stream
*************



===========
Description
===========



Deletes a stream and all its shards and data. You must shut down any applications that are operating on the stream before you delete the stream. If an application attempts to operate on a deleted stream, it will receive the exception ``ResourceNotFoundException`` .

 

If the stream is in the ``ACTIVE`` state, you can delete it. After a ``delete-stream`` request, the specified stream is in the ``DELETING`` state until Amazon Kinesis completes the deletion.

 

**Note:** Amazon Kinesis might continue to accept data read and write operations, such as  put-record ,  put-records , and  get-records , on a stream in the ``DELETING`` state until the stream deletion is complete.

 

When you delete a stream, any shards in that stream are also deleted, and any tags are dissociated from the stream.

 

You can use the  describe-stream operation to check the state of the stream, which is returned in ``StreamStatus`` .

 

 delete-stream has a limit of 5 transactions per second per account.



========
Synopsis
========

::

    delete-stream
  --stream-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None