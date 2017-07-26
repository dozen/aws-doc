[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift delete-cluster-security-group:


*****************************
delete-cluster-security-group
*****************************



===========
Description
===========



Deletes an Amazon Redshift security group. 

 

.. note::

  You cannot delete a security group that is associated with any clusters. You cannot delete the default security group.

 

For information about managing security groups, go to `Amazon Redshift Cluster Security Groups`_ in the *Amazon Redshift Cluster Management Guide* . 



========
Synopsis
========

::

    delete-cluster-security-group
  --cluster-security-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-security-group-name`` (string)


  The name of the cluster security group to be deleted. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Delete a Cluster Security Group
-------------------------------

This example deletes a cluster security group.

Command::

   aws redshift delete-cluster-security-group --cluster-security-group-name mysecuritygroup



======
Output
======

None

.. _Amazon Redshift Cluster Security Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-security-groups.html
