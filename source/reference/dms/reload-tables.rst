[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms reload-tables:


*************
reload-tables
*************



===========
Description
===========



Reloads the target database table with the source data. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/ReloadTables>`_


========
Synopsis
========

::

    reload-tables
  --replication-task-arn <value>
  --tables-to-reload <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-task-arn`` (string)


  The Amazon Resource Name (ARN) of the replication instance. 

  

``--tables-to-reload`` (list)


  The name and schema of the table to be reloaded. 

  



Shorthand Syntax::

    SchemaName=string,TableName=string ...




JSON Syntax::

  [
    {
      "SchemaName": "string",
      "TableName": "string"
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

ReplicationTaskArn -> (string)

  

  The Amazon Resource Name (ARN) of the replication task. 

  

  

