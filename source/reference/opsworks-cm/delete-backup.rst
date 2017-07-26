[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm delete-backup:


*************
delete-backup
*************



===========
Description
===========



Deletes a backup. You can delete both manual and automated backups. This operation is asynchronous. 

 

An ``InvalidStateException`` is thrown when a backup deletion is already in progress. A ``ResourceNotFoundException`` is thrown when the backup does not exist. A ``ValidationException`` is thrown when parameters of the request are not valid. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/DeleteBackup>`_


========
Synopsis
========

::

    delete-backup
  --backup-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--backup-id`` (string)


  The ID of the backup to delete. Run the describe-backups command to get a list of backup IDs. Backup IDs are in the format ``ServerName-yyyyMMddHHmmssSSS`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete backups**

The following ``delete-backup`` command deletes a manual or automated backup of
a Chef Automate server, identified by the backup ID. This command is useful when
you are approaching the maximum number of backups that you can save, or you want
to minimize your Amazon S3 storage costs.::

  aws opsworks-cm delete-backup --backup-id "automate-06-2016-11-19T23:42:40.240Z"

The output shows whether the backup deletion succeeded.

**More Information**

For more information, see `Back Up and Restore an AWS OpsWorks for Chef Automate Server`_ in the *AWS OpsWorks User Guide*.

.. _`Back Up and Restore an AWS OpsWorks for Chef Automate Server`: http://docs.aws.amazon.com/opsworks/latest/userguide/opscm-backup-restore.html



======
Output
======

