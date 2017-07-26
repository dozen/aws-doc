[ :ref:`aws <cli:aws>` . :ref:`athena <cli:aws athena>` ]

.. _cli:aws athena start-query-execution:


*********************
start-query-execution
*********************



===========
Description
===========



Runs (executes) the SQL query statements contained in the ``Query`` string.

 

For code samples using the AWS SDK for Java, see `Examples and Code Samples <http://docs.aws.amazon.com/athena/latest/ug/code-samples.html>`_ in the *Amazon Athena User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/athena-2017-05-18/StartQueryExecution>`_


========
Synopsis
========

::

    start-query-execution
  --query-string <value>
  [--client-request-token <value>]
  [--query-execution-context <value>]
  --result-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--query-string`` (string)


  The SQL query statements to be executed.

  

``--client-request-token`` (string)


  A unique case-sensitive string used to ensure the request to create the query is idempotent (executes only once). If another ``start-query-execution`` request is received, the same response is returned and another query is not created. If a parameter has changed, for example, the ``query-string`` , an error is returned.

   

  .. warning::

     

    This token is listed as not required because AWS SDKs (for example the AWS SDK for Java) auto-generate the token for users. If you are not using the AWS SDK or the AWS CLI, you must provide this token or the action will fail.

     

  

``--query-execution-context`` (structure)


  The database within which the query executes.

  



Shorthand Syntax::

    Database=string




JSON Syntax::

  {
    "Database": "string"
  }



``--result-configuration`` (structure)


  Specifies information about where and how to save the results of the query execution.

  



Shorthand Syntax::

    OutputLocation=string,EncryptionConfiguration={EncryptionOption=string,KmsKey=string}




JSON Syntax::

  {
    "OutputLocation": "string",
    "EncryptionConfiguration": {
      "EncryptionOption": "SSE_S3"|"SSE_KMS"|"CSE_KMS",
      "KmsKey": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

QueryExecutionId -> (string)

  

  The unique ID of the query that ran as a result of this request.

  

  

