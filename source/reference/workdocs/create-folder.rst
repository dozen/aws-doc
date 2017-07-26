[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs create-folder:


*************
create-folder
*************



===========
Description
===========



Creates a folder with the specified name and parent folder.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/CreateFolder>`_


========
Synopsis
========

::

    create-folder
  [--authentication-token <value>]
  [--name <value>]
  --parent-folder-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--name`` (string)


  The name of the new folder.

  

``--parent-folder-id`` (string)


  The ID of the parent folder.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Metadata -> (structure)

  

  The metadata of the folder.

  

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

    

    

  

