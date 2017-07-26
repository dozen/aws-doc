[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift delete-cluster-subnet-group:


***************************
delete-cluster-subnet-group
***************************



===========
Description
===========



Deletes the specified cluster subnet group. 



========
Synopsis
========

::

    delete-cluster-subnet-group
  --cluster-subnet-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-subnet-group-name`` (string)


  The name of the cluster subnet group name to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Delete a Cluster subnet Group
-----------------------------

This example deletes a cluster subnet group.

Command::

   aws redshift delete-cluster-subnet-group --cluster-subnet-group-name mysubnetgroup

Result::

    {
       "ResponseMetadata": {
          "RequestId": "253fbffd-6993-11e2-bc3a-47431073908a"
       }
    }




======
Output
======

None