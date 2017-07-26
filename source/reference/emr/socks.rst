[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr socks:


*****
socks
*****



===========
Description
===========

Create a socks tunnel on port 8157 from your machine to the master.

A value for the variable Key Pair File can be set in the AWS CLI config file using the "aws configure set" command.




========
Synopsis
========

::

    socks
  --cluster-id <value>
  --key-pair-file <value>




=======
Options
=======

``--cluster-id`` (string)
Cluster Id of cluster you want to ssh into

``--key-pair-file`` (string)
Private key file to use for login



========
Examples
========

The following command opens a socks connection with the master instance in a cluster with the cluster ID ``j-3SD91U2E1L2QX``::

  aws emr socks --cluster-id j-3SD91U2E1L2QX --key-pair-file ~/.ssh/mykey.pem

The key pair file option takes a local path to a private key file.