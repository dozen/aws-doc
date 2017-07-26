[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-placement-group:


**********************
delete-placement-group
**********************



===========
Description
===========



Deletes the specified placement group. You must terminate all instances in the placement group before you can delete the placement group. For more information about placement groups and cluster instances, see `Cluster Instances`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    delete-placement-group
  [--dry-run | --no-dry-run]
  --group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--group-name`` (string)


  The name of the placement group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a placement group**

This example command deletes the specified placement group.

Command::

  aws ec2 delete-placement-group --group-name my-cluster


======
Output
======

None

.. _Cluster Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using_cluster_computing.html
