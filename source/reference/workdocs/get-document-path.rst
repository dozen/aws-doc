[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs get-document-path:


*****************
get-document-path
*****************



===========
Description
===========



Retrieves the path information (the hierarchy from the root folder) for the requested document.

 

By default, Amazon WorkDocs returns a maximum of 100 levels upwards from the requested document and only includes the IDs of the parent folders in the path. You can limit the maximum number of levels. You can also request the names of the parent folders.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/GetDocumentPath>`_


========
Synopsis
========

::

    get-document-path
  [--authentication-token <value>]
  --document-id <value>
  [--limit <value>]
  [--fields <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--document-id`` (string)


  The ID of the document.

  

``--limit`` (integer)


  The maximum number of levels in the hierarchy to return.

  

``--fields`` (string)


  A comma-separated list of values. Specify ``NAME`` to include the names of the parent folders.

  

``--marker`` (string)


  This value is not supported.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Path -> (structure)

  

  The path information.

  

  Components -> (list)

    

    The components of the resource path.

    

    (structure)

      

      Describes the resource path.

      

      Id -> (string)

        

        The ID of the resource path.

        

        

      Name -> (string)

        

        The name of the resource path.

        

        

      

    

  

