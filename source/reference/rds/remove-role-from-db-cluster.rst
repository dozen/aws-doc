[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds remove-role-from-db-cluster:


***************************
remove-role-from-db-cluster
***************************



===========
Description
===========



Disassociates an Identity and Access Management (IAM) role from an Aurora DB cluster. For more information, see `Authorizing Amazon Aurora to Access Other AWS Services On Your Behalf <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Aurora.Authorizing.AWSServices.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/RemoveRoleFromDBCluster>`_


========
Synopsis
========

::

    remove-role-from-db-cluster
  --db-cluster-identifier <value>
  --role-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-identifier`` (string)


  The name of the DB cluster to disassociate the IAM role from.

  

``--role-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM role to disassociate from the Aurora DB cluster, for example ``arn:aws:iam::123456789012:role/AuroraAccessRole`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None