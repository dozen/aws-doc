[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr modify-instance-groups:


**********************
modify-instance-groups
**********************



===========
Description
===========



modify-instance-groups modifies the number of nodes and configuration settings of an instance group. The input parameters include the new target instance count for the group and the instance group ID. The call will either succeed or fail atomically.



========
Synopsis
========

::

    modify-instance-groups
  [--instance-groups <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-groups`` (list)


  Instance groups to change.

  



Shorthand Syntax::

    InstanceGroupId=string,InstanceCount=integer,EC2InstanceIdsToTerminate=string,string ...




JSON Syntax::

  [
    {
      "InstanceGroupId": "string",
      "InstanceCount": integer,
      "EC2InstanceIdsToTerminate": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None