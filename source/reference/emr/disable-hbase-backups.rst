[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr disable-hbase-backups:


*********************
disable-hbase-backups
*********************



===========
Description
===========

Add a step to disable automated HBase backups. This command is only available for AMI Versions (3.x and 2.x).



========
Synopsis
========

::

    disable-hbase-backups
  --cluster-id <value>
  [--full]
  [--incremental]




=======
Options
=======

``--cluster-id`` (string)


  A unique string that identifies the cluster. This identifier is returned by ``create-cluster`` and can also be obtained from ``list-clusters`` .

  

``--full`` (boolean)
Disables full backup.

``--incremental`` (boolean)
Disables incremental backup.

