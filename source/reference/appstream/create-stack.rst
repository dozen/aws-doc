[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream create-stack:


************
create-stack
************



===========
Description
===========



Create a new stack.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/CreateStack>`_


========
Synopsis
========

::

    create-stack
  --name <value>
  [--description <value>]
  [--display-name <value>]
  [--storage-connectors <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The unique identifier for this stack.

  

``--description`` (string)


  The description displayed to end users on the AppStream 2.0 portal.

  

``--display-name`` (string)


  The name displayed to end users on the AppStream 2.0 portal.

  

``--storage-connectors`` (list)


  The storage connectors to be enabled for the stack.

  



Shorthand Syntax::

    ConnectorType=string,ResourceIdentifier=string ...




JSON Syntax::

  [
    {
      "ConnectorType": "HOMEFOLDERS",
      "ResourceIdentifier": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Stack -> (structure)

  

  The details for the created stack.

  

  Arn -> (string)

    

    The ARN of the stack.

    

    

  Name -> (string)

    

    The unique identifier of the stack.

    

    

  Description -> (string)

    

    A meaningful description for the stack.

    

    

  DisplayName -> (string)

    

    A display name for the stack.

    

    

  CreatedTime -> (timestamp)

    

    The time stamp when the stack was created.

    

    

  StorageConnectors -> (list)

    

    The storage connectors to be enabled for the stack.

    

    (structure)

      

      Contains the parameters for a storage connector.

      

      ConnectorType -> (string)

        

        The type of storage connector. The possible values include: HOMEFOLDERS.

        

        

      ResourceIdentifier -> (string)

        

        The ARN associated with the storage connector.

        

        

      

    

  StackErrors -> (list)

    

    The list of errors associated with the stack.

    

    (structure)

      

      Contains the parameters for a stack error.

      

      ErrorCode -> (string)

        

        The error code of a stack error.

        

        

      ErrorMessage -> (string)

        

        The error message of a stack error.

        

        

      

    

  

