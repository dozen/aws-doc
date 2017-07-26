[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-placement-group:


**********************
create-placement-group
**********************



===========
Description
===========



Creates a placement group that you launch cluster instances into. You must give the group a name that's unique within the scope of your account.

 

For more information about placement groups and cluster instances, see `Cluster Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using_cluster_computing.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreatePlacementGroup>`_


========
Synopsis
========

::

    create-placement-group
  [--dry-run | --no-dry-run]
  --group-name <value>
  --strategy <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--group-name`` (string)


  A name for the placement group.

   

  Constraints: Up to 255 ASCII characters

  

``--strategy`` (string)


  The placement strategy.

  

  Possible values:

  
  *   ``cluster``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a placement group**

This example command creates a placement group with the specified name.

Command::

  aws ec2 create-placement-group --group-name my-cluster --strategy cluster


======
Output
======

None