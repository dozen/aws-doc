[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` . :ref:`wait <cli:aws emr wait>` ]

.. _cli:aws emr wait cluster-running:


***************
cluster-running
***************



===========
Description
===========

Wait until JMESPath query Cluster.Status.State returns RUNNING when polling with ``describe-cluster``. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 60 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/DescribeCluster>`_


========
Synopsis
========

::

    cluster-running
  --cluster-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The identifier of the cluster to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None