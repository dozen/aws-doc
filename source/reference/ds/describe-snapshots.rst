[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds describe-snapshots:


******************
describe-snapshots
******************



===========
Description
===========



Obtains information about the directory snapshots that belong to this account.

 

This operation supports pagination with the use of the *next-token* request and response parameters. If more results are available, the *DescribeSnapshots.NextToken* member contains a token that you pass in the next call to  describe-snapshots to retrieve the next set of items.

 

You can also specify a maximum number of return results with the *limit* parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DescribeSnapshots>`_


========
Synopsis
========

::

    describe-snapshots
  [--directory-id <value>]
  [--snapshot-ids <value>]
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory for which to retrieve snapshot information.

  

``--snapshot-ids`` (list)


  A list of identifiers of the snapshots to obtain the information for. If this member is null or empty, all snapshots are returned using the *limit* and *next-token* members.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The *DescribeSnapshotsResult.NextToken* value from a previous call to  describe-snapshots . Pass null if this is the first call.

  

``--limit`` (integer)


  The maximum number of objects to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Snapshots -> (list)

  

  The list of  Snapshot objects that were retrieved.

   

  It is possible that this list contains less than the number of items specified in the *limit* member of the request. This occurs if there are less than the requested number of items left to retrieve, or if the limitations of the operation have been exceeded.

  

  (structure)

    

    Describes a directory snapshot.

    

    DirectoryId -> (string)

      

      The directory identifier.

      

      

    SnapshotId -> (string)

      

      The snapshot identifier.

      

      

    Type -> (string)

      

      The snapshot type.

      

      

    Name -> (string)

      

      The descriptive name of the snapshot.

      

      

    Status -> (string)

      

      The snapshot status.

      

      

    StartTime -> (timestamp)

      

      The date and time that the snapshot was taken.

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value in the *next-token* member of a subsequent call to  describe-snapshots .

  

  

