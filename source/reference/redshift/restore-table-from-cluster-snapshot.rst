[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift restore-table-from-cluster-snapshot:


***********************************
restore-table-from-cluster-snapshot
***********************************



===========
Description
===========



Creates a new table from a table in an Amazon Redshift cluster snapshot. You must create the new table within the Amazon Redshift cluster that the snapshot was taken from.

 

You cannot use ``restore-table-from-cluster-snapshot`` to restore a table with the same name as an existing table in an Amazon Redshift cluster. That is, you cannot overwrite an existing table in a cluster with a restored table. If you want to replace your original table with a new, restored table, then rename or drop your original table before you call ``restore-table-from-cluster-snapshot`` . When you have renamed your original table, then you can pass the original name of the table as the ``NewTableName`` parameter value in the call to ``restore-table-from-cluster-snapshot`` . This way, you can replace the original table with the table created from the snapshot.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/RestoreTableFromClusterSnapshot>`_


========
Synopsis
========

::

    restore-table-from-cluster-snapshot
  --cluster-identifier <value>
  --snapshot-identifier <value>
  --source-database-name <value>
  [--source-schema-name <value>]
  --source-table-name <value>
  [--target-database-name <value>]
  [--target-schema-name <value>]
  --new-table-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-identifier`` (string)


  The identifier of the Amazon Redshift cluster to restore the table to.

  

``--snapshot-identifier`` (string)


  The identifier of the snapshot to restore the table from. This snapshot must have been created from the Amazon Redshift cluster specified by the ``ClusterIdentifier`` parameter.

  

``--source-database-name`` (string)


  The name of the source database that contains the table to restore from.

  

``--source-schema-name`` (string)


  The name of the source schema that contains the table to restore from. If you do not specify a ``SourceSchemaName`` value, the default is ``public`` .

  

``--source-table-name`` (string)


  The name of the source table to restore from.

  

``--target-database-name`` (string)


  The name of the database to restore the table to.

  

``--target-schema-name`` (string)


  The name of the schema to restore the table to.

  

``--new-table-name`` (string)


  The name of the table to create as a result of the current request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TableRestoreStatus -> (structure)

  

  Describes the status of a  restore-table-from-cluster-snapshot operation.

  

  TableRestoreRequestId -> (string)

    

    The unique identifier for the table restore request.

    

    

  Status -> (string)

    

    A value that describes the current state of the table restore request.

     

    Valid Values: ``SUCCEEDED`` , ``FAILED`` , ``CANCELED`` , ``PENDING`` , ``IN_PROGRESS``  

    

    

  Message -> (string)

    

    A description of the status of the table restore request. Status values include ``SUCCEEDED`` , ``FAILED`` , ``CANCELED`` , ``PENDING`` , ``IN_PROGRESS`` .

    

    

  RequestTime -> (timestamp)

    

    The time that the table restore request was made, in Universal Coordinated Time (UTC).

    

    

  ProgressInMegaBytes -> (long)

    

    The amount of data restored to the new table so far, in megabytes (MB).

    

    

  TotalDataInMegaBytes -> (long)

    

    The total amount of data to restore to the new table, in megabytes (MB).

    

    

  ClusterIdentifier -> (string)

    

    The identifier of the Amazon Redshift cluster that the table is being restored to.

    

    

  SnapshotIdentifier -> (string)

    

    The identifier of the snapshot that the table is being restored from.

    

    

  SourceDatabaseName -> (string)

    

    The name of the source database that contains the table being restored.

    

    

  SourceSchemaName -> (string)

    

    The name of the source schema that contains the table being restored.

    

    

  SourceTableName -> (string)

    

    The name of the source table being restored.

    

    

  TargetDatabaseName -> (string)

    

    The name of the database to restore the table to.

    

    

  TargetSchemaName -> (string)

    

    The name of the schema to restore the table to.

    

    

  NewTableName -> (string)

    

    The name of the table to create as a result of the table restore request.

    

    

  

