[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds list-schema-extensions:


**********************
list-schema-extensions
**********************



===========
Description
===========



Lists all schema extensions applied to a Microsoft AD Directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/ListSchemaExtensions>`_


========
Synopsis
========

::

    list-schema-extensions
  --directory-id <value>
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory from which to retrieve the schema extension information.

  

``--next-token`` (string)


  The ``ListSchemaExtensions.NextToken`` value from a previous call to ``list-schema-extensions`` . Pass null if this is the first call.

  

``--limit`` (integer)


  The maximum number of items to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SchemaExtensionsInfo -> (list)

  

  Information about the schema extensions applied to the directory.

  

  (structure)

    

    Information about a schema extension.

    

    DirectoryId -> (string)

      

      The identifier of the directory to which the schema extension is applied.

      

      

    SchemaExtensionId -> (string)

      

      The identifier of the schema extension.

      

      

    Description -> (string)

      

      A description of the schema extension.

      

      

    SchemaExtensionStatus -> (string)

      

      The current status of the schema extension.

      

      

    SchemaExtensionStatusReason -> (string)

      

      The reason for the ``SchemaExtensionStatus`` .

      

      

    StartDateTime -> (timestamp)

      

      The date and time that the schema extension started being applied to the directory.

      

      

    EndDateTime -> (timestamp)

      

      The date and time that the schema extension was completed.

      

      

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value for the ``next-token`` parameter in a subsequent call to ``list-schema-extensions`` to retrieve the next set of items.

  

  

