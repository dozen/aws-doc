[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr put:


***
put
***



===========
Description
===========

Put file onto the master node.

A value for the variable Key Pair File can be set in the AWS CLI config file using the "aws configure set emr.key_pair_file <value>" command.




========
Synopsis
========

::

    put
  --cluster-id <value>
  --key-pair-file <value>
  --src <value>
  [--dest <value>]




=======
Options
=======

``--cluster-id`` (string)
Cluster Id of cluster you want to put file onto

``--key-pair-file`` (string)
Private key file to use for login

``--src`` (string)
Source file path on local machine

``--dest`` (string)
Destination file path on remote host



========
Examples
========

The following command uploads a file named ``healthcheck.sh`` to the master instance in a cluster with the cluster ID ``j-3SD91U2E1L2QX``::

  aws emr put --cluster-id j-3SD91U2E1L2QX --key-pair-file ~/.ssh/mykey.pem --src ~/scripts/healthcheck.sh --dest /home/hadoop/bin/healthcheck.sh
