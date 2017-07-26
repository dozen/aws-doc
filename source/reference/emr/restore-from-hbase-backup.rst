[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr restore-from-hbase-backup:


*************************
restore-from-hbase-backup
*************************



===========
Description
===========

Restores HBase from S3. This command is only available for AMI Versions (3.x and 2.x).



========
Synopsis
========

::

    restore-from-hbase-backup
  --cluster-id <value>
  --dir <value>
  [--backup-version <value>]




=======
Options
=======

``--cluster-id`` (string)


  A unique string that identifies the cluster. This identifier is returned by ``create-cluster`` and can also be obtained from ``list-clusters`` .

  

``--dir`` (string)


  Amazon S3 location of the Hbase backup.

  Example:

  ``s3://mybucket/mybackup`` 

  

  where mybucket is the specified Amazon S3 bucket and mybackup is the specified backup location. The path argument must begin with s3:// in order to denote that the path argument refers to an Amazon S3 folder.

  

``--backup-version`` (string)


  Backup version to restore from. If not specified the latest backup in the specified location will be used.

  

