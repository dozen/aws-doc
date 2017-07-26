[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr wait:


****
wait
****



===========
Description
===========

Wait until a particular condition is satisfied.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  cluster-running
  cluster-terminated


========
Examples
========

The following command waits until a cluster with the cluster ID ``j-3SD91U2E1L2QX`` is up and running::

  aws emr wait cluster-running --cluster-id j-3SD91U2E1L2QX
