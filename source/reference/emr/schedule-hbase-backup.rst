[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr schedule-hbase-backup:


*********************
schedule-hbase-backup
*********************



===========
Description
===========

Adds a step to schedule automated HBase backup. This command is only available for AMI Versions (3.x and 2.x).



========
Synopsis
========

::

    schedule-hbase-backup
  --cluster-id <value>
  --type <value>
  --dir <value>
  --interval <value>
  --unit <value>
  [--start-time <value>]
  [--consistent]




=======
Options
=======

``--cluster-id`` (string)


  A unique string that identifies the cluster. This identifier is returned by ``create-cluster`` and can also be obtained from ``list-clusters`` .

  

``--type`` (string)


  Backup type. You can specify 'incremental' or 'full'.

  

``--dir`` (string)


  Amazon S3 location of the Hbase backup.

  Example:

  ``s3://mybucket/mybackup`` 

  

  where mybucket is the specified Amazon S3 bucket and mybackup is the specified backup location. The path argument must begin with s3:// in order to denote that the path argument refers to an Amazon S3 folder.

  

``--interval`` (string)


  The time between backups.

  

``--unit`` (string)


  The time unit for backup's time-interval. You can specify one of the following values: 'minutes', 'hours', or 'days'.

  

``--start-time`` (string)


  The time of the first backup in ISO format.

  e.g. 2014-04-21T05:26:10Z. Default is now.

``--consistent`` (boolean)


  Performs a consistent backup. Pauses all write operations to the HBase cluster during the backup process.

  



========
Examples
========

**1. To schedule a full hbase backup**

- Command::

    aws emr schedule-hbase-backup --cluster-id j-XXXXXXYY --type full --dir
    s3://myBucket/backup --interval 10 --unit hours --start-time
    2014-04-21T05:26:10Z --consistent

- Output::

    None

**2. To schedule an incremental hbase backup**

- Command::

    aws emr schedule-hbase-backup --cluster-id j-XXXXXXYY --type incremental
     --dir s3://myBucket/backup --interval 30 --unit minutes --start-time
    2014-04-21T05:26:10Z --consistent

- Output::

    None