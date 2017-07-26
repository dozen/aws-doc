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

   

 

For information about managing security groups, go to `Amazon Redshift Cluster Security Groups <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-security-groups.html>`_ in the *Amazon Redshift Cluster Management Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DeleteClusterSecurityGroup>`_


========
Synopsis
========

::

    delete-cluster-security-group
  --cluster-security-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-security-group-name`` (string)


  The name of the cluster security group to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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