[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr remove-auto-scaling-policy:


**************************
remove-auto-scaling-policy
**************************



===========
Description
===========



Removes an automatic scaling policy from a specified instance group within an EMR cluster.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/RemoveAutoScalingPolicy>`_


========
Synopsis
========

::

    remove-auto-scaling-policy
  --cluster-id <value>
  --instance-group-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  Specifies the ID of a cluster. The instance group to which the automatic scaling policy is applied is within this cluster.

  

``--instance-group-id`` (string)


  Specifies the ID of the instance group to which the scaling policy is applied.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

