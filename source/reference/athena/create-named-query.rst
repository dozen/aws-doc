[ :ref:`aws <cli:aws>` . :ref:`athena <cli:aws athena>` ]

.. _cli:aws athena create-named-query:


******************
create-named-query
******************



===========
Description
===========



Creates a named query.

 

For code samples using the AWS SDK for Java, see `Examples and Code Samples <http://docs.aws.amazon.com/athena/latest/ug/code-samples.html>`_ in the *Amazon Athena User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/athena-2017-05-18/CreateNamedQuery>`_


========
Synopsis
========

::

    create-named-query
  --name <value>
  [--description <value>]
  --database <value>
  --query-string <value>
  [--client-request-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The plain language name for the query.

  

``--description`` (string)


  A brief explanation of the query.

  

``--database`` (string)


  The database to which the query belongs.

  

``--query-string`` (string)


  The text of the query itself. In other words, all query statements.

  

``--client-request-token`` (string)


  A unique case-sensitive string used to ensure the request to create the query is idempotent (executes only once). If another ``create-named-query`` request is received, the same response is returned and another query is not created. If a parameter has changed, for example, the ``query-string`` , an error is returned.

   

  .. warning::

     

    This token is listed as not required because AWS SDKs (for example the AWS SDK for Java) auto-generate the token for users. If you are not using the AWS SDK or the AWS CLI, you must provide this token or the action will fail.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NamedQueryId -> (string)

  

  The unique ID of the query.

  

  

