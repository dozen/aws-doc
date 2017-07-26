[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr modify-instance-groups:


**********************
modify-instance-groups
**********************



===========
Description
===========



modify-instance-groups modifies the number of nodes and configuration settings of an instance group. The input parameters include the new target instance count for the group and the instance group ID. The call will either succeed or fail atomically.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/ModifyInstanceGroups>`_


========
Synopsis
========

::

    modify-instance-groups
  [--cluster-id <value>]
  [--instance-groups <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The ID of the cluster to which the instance group belongs.

  

``--instance-groups`` (list)


  Instance groups to change.

  



JSON Syntax::

  [
    {
      "InstanceGroupId": "string",
      "InstanceCount": integer,
      "EC2InstanceIdsToTerminate": ["string", ...],
      "ShrinkPolicy": {
        "DecommissionTimeout": integer,
        "InstanceResizePolicy": {
          "InstancesToTerminate": ["string", ...],
          "InstancesToProtect": ["string", ...],
          "InstanceTerminationTimeout": integer
        }
      }
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None