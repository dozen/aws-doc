[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs create-user:


***********
create-user
***********



===========
Description
===========



Creates a user in a Simple AD or Microsoft AD directory. The status of a newly created user is "ACTIVE". New users can access Amazon WorkDocs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/CreateUser>`_


========
Synopsis
========

::

    create-user
  [--organization-id <value>]
  --username <value>
  [--email-address <value>]
  --given-name <value>
  --surname <value>
  --password <value>
  [--time-zone-id <value>]
  [--storage-rule <value>]
  [--authentication-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--organization-id`` (string)


  The ID of the organization.

  

``--username`` (string)


  The login name of the user.

  

``--email-address`` (string)


  The email address of the user.

  

``--given-name`` (string)


  The given name of the user.

  

``--surname`` (string)


  The surname of the user.

  

``--password`` (string)


  The password of the user.

  

``--time-zone-id`` (string)


  The time zone ID of the user.

  

``--storage-rule`` (structure)


  The amount of storage for the user.

  



Shorthand Syntax::

    StorageAllocatedInBytes=long,StorageType=string




JSON Syntax::

  {
    "StorageAllocatedInBytes": long,
    "StorageType": "UNLIMITED"|"QUOTA"
  }



``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

User -> (structure)

  

  The user information.

  

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

        

        

      

    

  

