[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs describe-root-folders:


*********************
describe-root-folders
*********************



===========
Description
===========



Describes the current user's special folders; the ``RootFolder`` and the ``RecyleBin`` . ``RootFolder`` is the root of user's files and folders and ``RecyleBin`` is the root of recycled items. This is not a valid action for SigV4 (administrative API) clients.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/DescribeRootFolders>`_


========
Synopsis
========

::

    describe-root-folders
  --authentication-token <value>
  [--limit <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--limit`` (integer)


  The maximum number of items to return.

  

``--marker`` (string)


  The marker for the next set of results. (You received this marker from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Folders -> (list)

  

  The user's special folders.

  

  (structure)

    

    Describes a folder.

    

    Id -> (string)

      

      The ID of the folder.

      

      

    Name -> (string)

      

      The name of the folder.

      

      

    CreatorId -> (string)

      

      The ID of the creator.

      

      

    ParentFolderId -> (string)

      

      The ID of the parent folder.

      

      

    CreatedTimestamp -> (timestamp)

      

      The time when the folder was created.

      

      

    ModifiedTimestamp -> (timestamp)

      

      The time when the folder was updated.

      

      

    ResourceState -> (string)

      

      The resource state of the folder.

      

      

    Signature -> (string)

      

      The unique identifier created from the subfolders and documents of the folder.

      

      

    Labels -> (list)

      

      List of labels on the folder.

      

      (string)

        

        

      

    Size -> (long)

      

      The size of the folder metadata.

      

      

    LatestVersionSize -> (long)

      

      The size of the latest version of the folder metadata.

      

      

    

  

Marker -> (string)

  

  The marker for the next set of results.

  

  

