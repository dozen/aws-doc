[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr create-hbase-backup:


*******************
create-hbase-backup
*******************



===========
Description
===========

Creates a HBase backup in S3. This command is only available for AMI Versions (3.x and 2.x).



========
Synopsis
========

::

    create-hbase-backup
  --cluster-id <value>
  --dir <value>
  [--consistent]




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

  

``--consistent`` (boolean)


  Performs a consistent backup. Pauses all write operations to the HBase cluster during the backup process.

  

