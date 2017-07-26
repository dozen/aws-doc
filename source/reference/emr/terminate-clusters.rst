[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr terminate-clusters:


******************
terminate-clusters
******************



===========
Description
===========

Shuts down a list of clusters. When a cluster is shut down, any step not yet completed is canceled and the Amazon EC2 instances in the cluster are terminated. Any log files not already saved are uploaded to Amazon S3 if a LogUri was specified when the cluster was created. 'terminate-clusters' is asynchronous. Depending on the configuration of the cluster, it may take from 5 to 20 minutes for the cluster to completely terminate and release allocated resources such as Amazon EC2 instances.



========
Synopsis
========

::

    terminate-clusters
  --cluster-ids <value> [<value>...]




=======
Options
=======

``--cluster-ids`` (list)


  A list of clusters to terminate.

  



Syntax::

  "string" "string" ...



