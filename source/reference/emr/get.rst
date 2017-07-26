[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr get:


***
get
***



===========
Description
===========

Get file from master node.

A value for the variable Key Pair File can be set in the AWS CLI config file using the "aws configure set" command.




========
Synopsis
========

::

    get
  --cluster-id <value>
  --key-pair-file <value>
  --src <value>
  [--dest <value>]




=======
Options
=======

``--cluster-id`` (string)
Cluster Id of cluster you want to get file from

``--key-pair-file`` (string)
Private key file to use for login

``--src`` (string)
Source file path on remote host

``--dest`` (string)
Destination file path on your machine



========
Examples
========

The following downloads the ``hadoop-examples.jar`` archive from the master instance in a cluster with the cluster ID ``j-3SD91U2E1L2QX``::

  aws emr get --cluster-id j-3SD91U2E1L2QX --key-pair-file ~/.ssh/mykey.pem --src /home/hadoop-examples.jar --dest ~
