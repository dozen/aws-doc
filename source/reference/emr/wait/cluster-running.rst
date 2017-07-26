[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` . :ref:`wait <cli:aws emr wait>` ]

.. _cli:aws emr wait cluster-running:


***************
cluster-running
***************



===========
Description
===========

Wait until JMESPath query Cluster.Status.State returns RUNNING when polling with ``describe-cluster``. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 60 failed checks.

========
Synopsis
========

::

    cluster-running
  --cluster-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-id`` (string)


  The identifier of the cluster to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None