[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs create-comment:


**************
create-comment
**************



===========
Description
===========



Adds a new comment to the specified document version.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/CreateComment>`_


========
Synopsis
========

::

    create-comment
  [--authentication-token <value>]
  --document-id <value>
  --version-id <value>
  [--parent-id <value>]
  [--thread-id <value>]
  --text <value>
  [--visibility <value>]
  [--notify-collaborators | --no-notify-collaborators]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--document-id`` (string)


  The ID of the document.

  

``--version-id`` (string)


  The ID of the document version.

  

``--parent-id`` (string)


  The ID of the parent comment.

  

``--thread-id`` (string)


  The ID of the root comment in the thread.

  

``--text`` (string)


  The text of the comment.

  

``--visibility`` (string)


  The visibility of the comment. Options are either PRIVATE, where the comment is visible only to the comment author and document owner and co-owners, or PUBLIC, where the comment is visible to document owners, co-owners, and contributors.

  

  Possible values:

  
  *   ``PUBLIC``

  
  *   ``PRIVATE``

  

  

``--notify-collaborators`` | ``--no-notify-collaborators`` (boolean)


  Set this parameter to TRUE to send an email out to the document collaborators after the comment is created.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Comment -> (structure)

  

  The comment that has been created.

  

  CommentId -> (string)

    

    The ID of the comment.

    

    

  ParentId -> (string)

    

    The ID of the parent comment.

    

    

  ThreadId -> (string)

    

    The ID of the root comment in the thread.

    

    

  Text -> (string)

    

    The text of the comment.

    

    

  Contributor -> (structure)

    

    The details of the user who made the comment.

    

    Id -> (string)

      

      The ID of the user.

      

      

    Username -> (string)

      

      The login name of the user.

      

      

    EmailAddress -> (string)

      

      The email address of the user.

      

      

    GivenName -> (string)

      

      The given name of the user.

      

      

    Surname -> (string)

      

      The surname of the user.

      

      

    OrganizationId -> (string)

      

      The ID of the organization.

      

      

    RootFolderId -> (string)

      

      The ID of the root folder.

      

      

    RecycleBinFolderId -> (string)

      

      The ID of the recycle bin folder.

      

      

    Status -> (string)

      

      The status of the user.

      

      

    Type -> (string)

      

      The type of user.

      

      

    CreatedTimestamp -> (timestamp)

      

      The time when the user was created.

      

      

    ModifiedTimestamp -> (timestamp)

      

      The time when the user was modified.

      

      

    TimeZoneId -> (string)

      

      The time zone ID of the user.

      

      

    Locale -> (string)

      

      The locale of the user.

      

      

    Storage -> (structure)

      

      The storage for the user.

      

      StorageUtilizedInBytes -> (long)

        

        The amount of storage utilized, in bytes.

        

        

      StorageRule -> (structure)

        

        The storage for a user.

        

        StorageAllocatedInBytes -> (long)

          

          The amount of storage allocated, in bytes.

          

          

        StorageType -> (string)

          

          The type of storage.

          

          

        

      

    

  CreatedTimestamp -> (timestamp)

    

    The time that the comment was created.

    

    

  Status -> (string)

    

    The status of the comment.

    

    

  Visibility -> (string)

    

    The visibility of the comment. Options are either PRIVATE, where the comment is visible only to the comment author and document owner and co-owners, or PUBLIC, where the comment is visible to document owners, co-owners, and contributors.

    

    

  RecipientId -> (string)

    

    If the comment is a reply to another user's comment, this field contains the user ID of the user being replied to.

    

    

  

