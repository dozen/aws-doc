[ :ref:`aws <cli:aws>` . :ref:`athena <cli:aws athena>` ]

.. _cli:aws athena get-named-query:


***************
get-named-query
***************



===========
Description
===========



Returns information about a single query.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/athena-2017-05-18/GetNamedQuery>`_


========
Synopsis
========

::

    get-named-query
  --named-query-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--named-query-id`` (string)


  The unique ID of the query. Use  list-named-queries to get query IDs.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NamedQuery -> (structure)

  

  Information about the query.

  

  Name -> (string)

    

    The plain-language name of the query.

    

    

  Description -> (string)

    

    A brief description of the query.

    

    

  Database -> (string)

    

    The database to which the query belongs.

    

    

  QueryString -> (string)

    

    The SQL query statements that comprise the query.

    

    

  NamedQueryId -> (string)

    

    The unique identifier of the query.

    

    

  

